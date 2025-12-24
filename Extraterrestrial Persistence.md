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

ในส่วนของข้อนี้ ไฟล์ที่ชื่อว่า "persistence.sh"

เดี่ยวมาต่อ ขอไปนอนก่อน...

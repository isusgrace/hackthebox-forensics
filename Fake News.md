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
```
┌──(kali㉿kali)-[~]
└─$ cd Downloads
                                                                                                               
┌──(kali㉿kali)-[~/Downloads]
└─$ mkdir Fake_News01
                                                                                                               
┌──(kali㉿kali)-[~/Downloads]
└─$ cd Fake_News01
                                                                                                               
┌──(kali㉿kali)-[~/Downloads/Fake_News01]
└─$ wget "https://labs.hackthebox.com/api/v4/challenge/download/440?auth_user_id=2469954&expires=1766114941&signature=3cf0ca7f1ef0ddc36180c2403d03c632c94d5fc77db9791525648278f18a7774"
--2025-12-18 21:29:04--  https://labs.hackthebox.com/api/v4/challenge/download/440?auth_user_id=2469954&expires=1766114941&signature=3cf0ca7f1ef0ddc36180c2403d03c632c94d5fc77db9791525648278f18a7774
Resolving labs.hackthebox.com (labs.hackthebox.com)... 109.176.239.70, 109.176.239.69
Connecting to labs.hackthebox.com (labs.hackthebox.com)|109.176.239.70|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 32095305 (31M) [application/zip]
Saving to: ‘440?auth_user_id=2469954&expires=1766114941&signature=3cf0ca7f1ef0ddc36180c2403d03c632c94d5fc77db9791525648278f18a7774’

440?auth_user_id=2469954&ex 100%[==========================================>]  30.61M  4.81MB/s    in 6.4s    

2025-12-18 21:29:12 (4.79 MB/s) - ‘440?auth_user_id=2469954&expires=1766114941&signature=3cf0ca7f1ef0ddc36180c2403d03c632c94d5fc77db9791525648278f18a7774’ saved [32095305/32095305]
```

Step 2 unzip

ข้อนี้จะให้ไฟล์ .zip มาให้ ให้เราทำการแตกไฟล์ด้วยการใช้คำสั่ง unzip 

password คือ hackthebox

```
unzip FakeNews.zip
```

Step 3 Directory html

หลังจากที่เราทำการแตกไฟล์ .zip เราจะได้ไดเรกทอรีมา 1 ไดเรกทอรี ชื่อ"html"

ให้เราทำการใช้คำสั่ง cd 

```
cd html
```

คำสั่ง cd ใช้สำหรับเปลี่ยนไดเรกทอรีหรือโฟลเดอร์ปัจจุบันในเทอร์มินัล

หลังจากนั้นเราจะใช้คำสั่ง ls เพื่อดูไฟล์และไดเรกทอรีย่อยที่อยู่ในไดเรกทอรี html 

```
┌──(kali㉿kali)-[~/Downloads/Fake_News/html]
└─$ ls
index.php        wp-admin              wp-config-docker.php  wp-cron.php        wp-login.php     wp-trackback.php
license.txt      wp-blog-header.php    wp-config.php         wp-includes        wp-mail.php      xmlrpc.php
readme.html      wp-blogs              wp-config-sample.php  wp-links-opml.php  wp-settings.php
wp-activate.php  wp-comments-post.php  wp-content            wp-load.php        wp-signup.php
```

คำสั่ง ls ใช้แสดงรายการไฟล์และไดเรกทอรีที่มีอยู่ในไดเรกทอรีปัจจุบัน


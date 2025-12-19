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
ต่อ

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


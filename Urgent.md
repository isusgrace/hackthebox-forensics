Hi, Can you speak Thai ?

Yes, I can speak Thai.

มา วันนี้เราจะมาทำข้อ Urgent หมวด Forensics ระดับ Very easy

Step 1 Outlook

1.1 ดาวน์โหลดไฟล์จาก hackthebox

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7cbe14ff-a386-4feb-841a-344d55a36c26" />

1.2 สังเกตที่ Type จะเป็น E-mail Message จากนั้นคลิก 2 ครั้ง เพื่อเปิดใน Outlook 

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b7298a72-9115-48de-9246-899be795f11b" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8a8c8c59-9af5-4016-a399-f8d9cbfcedc6" />

1.3 สังเกตที่ onlineform.html จากนั้นกดลูกศรชี้ลง มันอยู่ข้างไฟล์ทางด้านขวามือ แล้วเลือก save as จะ save ไว้ที่ไหนก็ได้ ขอแค่เปิดไฟล์ได้ ฉันเลือก save ไว้ที่ Downloads

Step 2 404 Not Found

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5cb312ae-ad66-41e0-82a4-298ae3dd9355" />

2.1 คลิกขวา 1 ครั้ง แล้วเลือก View page source

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/17f9f6bb-737c-42ab-9a25-c4cc4a6b2613" />

<img width="1920" height="1080" alt="urgent cap" src="https://github.com/user-attachments/assets/da269282-512c-41b5-9a9e-b31e409d760b" />

2.2 สังเกตบรรทัดสีฟ้าเข้มที่ฉันเลือก ให้คัดลอกแล้วมาวางในหน้า Input ของ CyberChef ค้นหา URL Decode ลากมาวางในหน้า Recipe จากนั้นเลื่อนหน้า Output ลงมาเรื่อย ๆ ก็จะเห็น flag

XXXXX ไม่ใช่ flag นะ คือปิดไว้ จะได้ทำเอง

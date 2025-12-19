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

                                                                                                               
┌──(kali㉿kali)-[~/Downloads/Fake_News01]
└─$ ls               
'440?auth_user_id=2469954&expires=1766114941&signature=3cf0ca7f1ef0ddc36180c2403d03c632c94d5fc77db9791525648278f18a7774'
                                                                                                               
┌──(kali㉿kali)-[~/Downloads/Fake_News01]
└─$ mv '440?auth_user_id=2469954&expires=1766114941&signature=3cf0ca7f1ef0ddc36180c2403d03c632c94d5fc77db9791525648278f18a7774' FakeNews01.zip
                                                                                                               
┌──(kali㉿kali)-[~/Downloads/Fake_News01]
└─$ ls
FakeNews01.zip
```

Step 2 unzip

ข้อนี้จะให้ไฟล์ .zip มาให้ ให้เราทำการแตกไฟล์ด้วยการใช้คำสั่ง unzip 

password คือ hackthebox

```
unzip FakeNews01.zip
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
┌──(kali㉿kali)-[~/Downloads/Fake_News01]
└─$ cd html       
                                                                                                               
┌──(kali㉿kali)-[~/Downloads/Fake_News01/html]
└─$ ls
index.php        wp-blog-header.php    wp-config-sample.php  wp-load.php      wp-trackback.php
license.txt      wp-blogs              wp-content            wp-login.php     xmlrpc.php
readme.html      wp-comments-post.php  wp-cron.php           wp-mail.php
wp-activate.php  wp-config-docker.php  wp-includes           wp-settings.php
wp-admin         wp-config.php         wp-links-opml.php     wp-signup.php
```

คำสั่ง ls ใช้แสดงรายการไฟล์และไดเรกทอรีที่มีอยู่ในไดเรกทอรีปัจจุบัน

wp-admin, wp-blogs, wp-content, wp-includes คือไดเรกทอรี ที่เหลือเป็นไฟล์

ต่อมาเราจะใช้คำสั่ง tree คำสั่งนี้ใช้เพื่อแสดงโครงสร้างไดเรกทอรีและไฟล์ทั้งหมดในระบบไฟล์คอมพิวเตอร์ให้อยู่ในรูปแบบของโครงสร้างต้นไม้

```
┌──(kali㉿kali)-[~/Downloads/Fake_News/html]
└─$ tree
.
├── index.php
├── license.txt
├── readme.html
├── wp-activate.php
├── wp-admin
│   ├── about.php
│   ├── admin-ajax.php
│   ├── admin-footer.php
│   ├── admin-functions.php
│   ├── admin-header.php
│   ├── admin.php
│   ├── admin-post.php
│   ├── async-upload.php
│   ├── authorize-application.php
│   ├── comment.php
│   ├── credits.php
│   ├── css
│   │   ├── about.css
│   │   ├── about.min.css
│   │   ├── about-rtl.css
│   │   ├── about-rtl.min.css
│   │   ├── admin-menu.css
│   │   ├── admin-menu.min.css
│   │   ├── admin-menu-rtl.css
│   │   ├── admin-menu-rtl.min.css
│   │   ├── code-editor.css
│   │   ├── code-editor.min.css
│   │   ├── code-editor-rtl.css
│   │   ├── code-editor-rtl.min.css
│   │   ├── color-picker.css
│   │   ├── color-picker.min.css
│   │   ├── color-picker-rtl.css
│   │   ├── color-picker-rtl.min.css
│   │   ├── colors
│   │   │   ├── _admin.scss
│   │   │   ├── blue
│   │   │   │   ├── colors.css
│   │   │   │   ├── colors.min.css
│   │   │   │   ├── colors-rtl.css
│   │   │   │   ├── colors-rtl.min.css
│   │   │   │   └── colors.scss
│   │   │   ├── coffee
│   │   │   │   ├── colors.css
│   │   │   │   ├── colors.min.css
│   │   │   │   ├── colors-rtl.css
│   │   │   │   ├── colors-rtl.min.css
│   │   │   │   └── colors.scss
│   │   │   ├── ectoplasm
│   │   │   │   ├── colors.css
│   │   │   │   ├── colors.min.css
│   │   │   │   ├── colors-rtl.css
│   │   │   │   ├── colors-rtl.min.css
│   │   │   │   └── colors.scss
│   │   │   ├── light
│   │   │   │   ├── colors.css
│   │   │   │   ├── colors.min.css
│   │   │   │   ├── colors-rtl.css
│   │   │   │   ├── colors-rtl.min.css
│   │   │   │   └── colors.scss
│   │   │   ├── midnight
│   │   │   │   ├── colors.css
│   │   │   │   ├── colors.min.css
│   │   │   │   ├── colors-rtl.css
│   │   │   │   ├── colors-rtl.min.css
│   │   │   │   └── colors.scss
│   │   │   ├── _mixins.scss
│   │   │   ├── modern
│   │   │   │   ├── colors.css
│   │   │   │   ├── colors.min.css
│   │   │   │   ├── colors-rtl.css
│   │   │   │   ├── colors-rtl.min.css
│   │   │   │   └── colors.scss
│   │   │   ├── ocean
│   │   │   │   ├── colors.css
│   │   │   │   ├── colors.min.css
│   │   │   │   ├── colors-rtl.css
│   │   │   │   ├── colors-rtl.min.css
│   │   │   │   └── colors.scss
│   │   │   ├── sunrise
│   │   │   │   ├── colors.css
│   │   │   │   ├── colors.min.css
│   │   │   │   ├── colors-rtl.css
│   │   │   │   ├── colors-rtl.min.css
│   │   │   │   └── colors.scss
│   │   │   └── _variables.scss
│   │   ├── common.css
│   │   ├── common.min.css
│   │   ├── common-rtl.css
│   │   ├── common-rtl.min.css
│   │   ├── customize-controls.css
│   │   ├── customize-controls.min.css
│   │   ├── customize-controls-rtl.css
│   │   ├── customize-controls-rtl.min.css
│   │   ├── customize-nav-menus.css
│   │   ├── customize-nav-menus.min.css
│   │   ├── customize-nav-menus-rtl.css
│   │   ├── customize-nav-menus-rtl.min.css
│   │   ├── customize-widgets.css
│   │   ├── customize-widgets.min.css
│   │   ├── customize-widgets-rtl.css
│   │   ├── customize-widgets-rtl.min.css
│   │   ├── dashboard.css
│   │   ├── dashboard.min.css
│   │   ├── dashboard-rtl.css
│   │   ├── dashboard-rtl.min.css
│   │   ├── deprecated-media.css
│   │   ├── deprecated-media.min.css
│   │   ├── deprecated-media-rtl.css
│   │   ├── deprecated-media-rtl.min.css
│   │   ├── edit.css
│   │   ├── edit.min.css
│   │   ├── edit-rtl.css
│   │   ├── edit-rtl.min.css
│   │   ├── farbtastic.css
│   │   ├── farbtastic.min.css
│   │   ├── farbtastic-rtl.css
│   │   ├── farbtastic-rtl.min.css
│   │   ├── forms.css
│   │   ├── forms.min.css
│   │   ├── forms-rtl.css
│   │   ├── forms-rtl.min.css
│   │   ├── install.css
│   │   ├── install.min.css
│   │   ├── install-rtl.css
│   │   ├── install-rtl.min.css
│   │   ├── l10n.css
│   │   ├── l10n.min.css
│   │   ├── l10n-rtl.css
│   │   ├── l10n-rtl.min.css
│   │   ├── list-tables.css
│   │   ├── list-tables.min.css
│   │   ├── list-tables-rtl.css
│   │   ├── list-tables-rtl.min.css
│   │   ├── login.css
│   │   ├── login.min.css
│   │   ├── login-rtl.css
│   │   ├── login-rtl.min.css
│   │   ├── media.css
│   │   ├── media.min.css
│   │   ├── media-rtl.css
│   │   ├── media-rtl.min.css
│   │   ├── nav-menus.css
│   │   ├── nav-menus.min.css
│   │   ├── nav-menus-rtl.css
│   │   ├── nav-menus-rtl.min.css
│   │   ├── revisions.css
│   │   ├── revisions.min.css
│   │   ├── revisions-rtl.css
│   │   ├── revisions-rtl.min.css
│   │   ├── site-health.css
│   │   ├── site-health.min.css
│   │   ├── site-health-rtl.css
│   │   ├── site-health-rtl.min.css
│   │   ├── site-icon.css
│   │   ├── site-icon.min.css
│   │   ├── site-icon-rtl.css
│   │   ├── site-icon-rtl.min.css
│   │   ├── themes.css
│   │   ├── themes.min.css
│   │   ├── themes-rtl.css
│   │   ├── themes-rtl.min.css
│   │   ├── widgets.css
│   │   ├── widgets.min.css
│   │   ├── widgets-rtl.css
│   │   ├── widgets-rtl.min.css
│   │   ├── wp-admin.css
│   │   ├── wp-admin.min.css
│   │   ├── wp-admin-rtl.css
│   │   └── wp-admin-rtl.min.css
│   ├── custom-background.php
│   ├── custom-header.php
│   ├── customize.php
│   ├── edit-comments.php
│   ├── edit-form-advanced.php
│   ├── edit-form-blocks.php
│   ├── edit-form-comment.php
│   ├── edit-link-form.php
│   ├── edit.php
│   ├── edit-tag-form.php
│   ├── edit-tags.php
│   ├── erase-personal-data.php
│   ├── export-personal-data.php
│   ├── export.php
│   ├── freedoms.php
│   ├── images
│   │   ├── about-header-about.svg
│   │   ├── about-header-credits.svg
│   │   ├── about-header-freedoms.svg
│   │   ├── about-header-privacy.svg
│   │   ├── about-texture.png
│   │   ├── align-center-2x.png
│   │   ├── align-center.png
│   │   ├── align-left-2x.png
│   │   ├── align-left.png
│   │   ├── align-none-2x.png
│   │   ├── align-none.png
│   │   ├── align-right-2x.png
│   │   ├── align-right.png
│   │   ├── arrows-2x.png
│   │   ├── arrows.png
│   │   ├── browser.png
│   │   ├── browser-rtl.png
│   │   ├── bubble_bg-2x.gif
│   │   ├── bubble_bg.gif
│   │   ├── comment-grey-bubble-2x.png
│   │   ├── comment-grey-bubble.png
│   │   ├── date-button-2x.gif
│   │   ├── date-button.gif
│   │   ├── freedom-1.svg
│   │   ├── freedom-2.svg
│   │   ├── freedom-3.svg
│   │   ├── freedom-4.svg
│   │   ├── generic.png
│   │   ├── icons32-2x.png
│   │   ├── icons32.png
│   │   ├── icons32-vs-2x.png
│   │   ├── icons32-vs.png
│   │   ├── imgedit-icons-2x.png
│   │   ├── imgedit-icons.png
│   │   ├── list-2x.png
│   │   ├── list.png
│   │   ├── loading.gif
│   │   ├── marker.png
│   │   ├── mask.png
│   │   ├── media-button-2x.png
│   │   ├── media-button-image.gif
│   │   ├── media-button-music.gif
│   │   ├── media-button-other.gif
│   │   ├── media-button.png
│   │   ├── media-button-video.gif
│   │   ├── menu-2x.png
│   │   ├── menu.png
│   │   ├── menu-vs-2x.png
│   │   ├── menu-vs.png
│   │   ├── no.png
│   │   ├── post-formats32.png
│   │   ├── post-formats32-vs.png
│   │   ├── post-formats.png
│   │   ├── post-formats-vs.png
│   │   ├── privacy.svg
│   │   ├── resize-2x.gif
│   │   ├── resize.gif
│   │   ├── resize-rtl-2x.gif
│   │   ├── resize-rtl.gif
│   │   ├── se.png
│   │   ├── sort-2x.gif
│   │   ├── sort.gif
│   │   ├── spinner-2x.gif
│   │   ├── spinner.gif
│   │   ├── stars-2x.png
│   │   ├── stars.png
│   │   ├── wheel.png
│   │   ├── w-logo-blue.png
│   │   ├── w-logo-white.png
│   │   ├── wordpress-logo.png
│   │   ├── wordpress-logo.svg
│   │   ├── wordpress-logo-white.svg
│   │   ├── wpspin_light-2x.gif
│   │   ├── wpspin_light.gif
│   │   ├── xit-2x.gif
│   │   ├── xit.gif
│   │   └── yes.png
│   ├── import.php
│   ├── includes
│   │   ├── admin-filters.php
│   │   ├── admin.php
│   │   ├── ajax-actions.php
│   │   ├── bookmark.php
│   │   ├── class-automatic-upgrader-skin.php
│   │   ├── class-bulk-plugin-upgrader-skin.php
│   │   ├── class-bulk-theme-upgrader-skin.php
│   │   ├── class-bulk-upgrader-skin.php
│   │   ├── class-core-upgrader.php
│   │   ├── class-custom-background.php
│   │   ├── class-custom-image-header.php
│   │   ├── class-file-upload-upgrader.php
│   │   ├── class-ftp.php
│   │   ├── class-ftp-pure.php
│   │   ├── class-ftp-sockets.php
│   │   ├── class-language-pack-upgrader.php
│   │   ├── class-language-pack-upgrader-skin.php
│   │   ├── class-pclzip.php
│   │   ├── class-plugin-installer-skin.php
│   │   ├── class-plugin-upgrader.php
│   │   ├── class-plugin-upgrader-skin.php
│   │   ├── class-theme-installer-skin.php
│   │   ├── class-theme-upgrader.php
│   │   ├── class-theme-upgrader-skin.php
│   │   ├── class-walker-category-checklist.php
│   │   ├── class-walker-nav-menu-checklist.php
│   │   ├── class-walker-nav-menu-edit.php
│   │   ├── class-wp-ajax-upgrader-skin.php
│   │   ├── class-wp-application-passwords-list-table.php
│   │   ├── class-wp-automatic-updater.php
│   │   ├── class-wp-comments-list-table.php
│   │   ├── class-wp-community-events.php
│   │   ├── class-wp-debug-data.php
│   │   ├── class-wp-filesystem-base.php
│   │   ├── class-wp-filesystem-direct.php
│   │   ├── class-wp-filesystem-ftpext.php
│   │   ├── class-wp-filesystem-ftpsockets.php
│   │   ├── class-wp-filesystem-ssh2.php
│   │   ├── class-wp-importer.php
│   │   ├── class-wp-internal-pointers.php
│   │   ├── class-wp-links-list-table.php
│   │   ├── class-wp-list-table-compat.php
│   │   ├── class-wp-list-table.php
│   │   ├── class-wp-media-list-table.php
│   │   ├── class-wp-ms-sites-list-table.php
│   │   ├── class-wp-ms-themes-list-table.php
│   │   ├── class-wp-ms-users-list-table.php
│   │   ├── class-wp-plugin-install-list-table.php
│   │   ├── class-wp-plugins-list-table.php
│   │   ├── class-wp-post-comments-list-table.php
│   │   ├── class-wp-posts-list-table.php
│   │   ├── class-wp-privacy-data-export-requests-list-table.php
│   │   ├── class-wp-privacy-data-removal-requests-list-table.php
│   │   ├── class-wp-privacy-policy-content.php
│   │   ├── class-wp-privacy-requests-table.php
│   │   ├── class-wp-screen.php
│   │   ├── class-wp-site-health-auto-updates.php
│   │   ├── class-wp-site-health.php
│   │   ├── class-wp-site-icon.php
│   │   ├── class-wp-terms-list-table.php
│   │   ├── class-wp-theme-install-list-table.php
│   │   ├── class-wp-themes-list-table.php
│   │   ├── class-wp-upgrader.php
│   │   ├── class-wp-upgrader-skin.php
│   │   ├── class-wp-upgrader-skins.php
│   │   ├── class-wp-users-list-table.php
│   │   ├── comment.php
│   │   ├── continents-cities.php
│   │   ├── credits.php
│   │   ├── dashboard.php
│   │   ├── deprecated.php
│   │   ├── edit-tag-messages.php
│   │   ├── export.php
│   │   ├── file.php
│   │   ├── image-edit.php
│   │   ├── image.php
│   │   ├── import.php
│   │   ├── list-table.php
│   │   ├── media.php
│   │   ├── menu.php
│   │   ├── meta-boxes.php
│   │   ├── misc.php
│   │   ├── ms-admin-filters.php
│   │   ├── ms-deprecated.php
│   │   ├── ms.php
│   │   ├── nav-menu.php
│   │   ├── network.php
│   │   ├── noop.php
│   │   ├── options.php
│   │   ├── plugin-install.php
│   │   ├── plugin.php
│   │   ├── post.php
│   │   ├── privacy-tools.php
│   │   ├── revision.php
│   │   ├── schema.php
│   │   ├── screen.php
│   │   ├── taxonomy.php
│   │   ├── template.php
│   │   ├── theme-install.php
│   │   ├── theme.php
│   │   ├── translation-install.php
│   │   ├── update-core.php
│   │   ├── update.php
│   │   ├── upgrade.php
│   │   ├── user.php
│   │   └── widgets.php
│   ├── index.php
│   ├── install-helper.php
│   ├── install.php
│   ├── js
│   │   ├── accordion.js
│   │   ├── accordion.min.js
│   │   ├── application-passwords.js
│   │   ├── application-passwords.min.js
│   │   ├── auth-app.js
│   │   ├── auth-app.min.js
│   │   ├── code-editor.js
│   │   ├── code-editor.min.js
│   │   ├── color-picker.js
│   │   ├── color-picker.min.js
│   │   ├── comment.js
│   │   ├── comment.min.js
│   │   ├── common.js
│   │   ├── common.min.js
│   │   ├── custom-background.js
│   │   ├── custom-background.min.js
│   │   ├── custom-header.js
│   │   ├── customize-controls.js
│   │   ├── customize-controls.min.js
│   │   ├── customize-nav-menus.js
│   │   ├── customize-nav-menus.min.js
│   │   ├── customize-widgets.js
│   │   ├── customize-widgets.min.js
│   │   ├── dashboard.js
│   │   ├── dashboard.min.js
│   │   ├── edit-comments.js
│   │   ├── edit-comments.min.js
│   │   ├── editor-expand.js
│   │   ├── editor-expand.min.js
│   │   ├── editor.js
│   │   ├── editor.min.js
│   │   ├── farbtastic.js
│   │   ├── gallery.js
│   │   ├── gallery.min.js
│   │   ├── image-edit.js
│   │   ├── image-edit.min.js
│   │   ├── inline-edit-post.js
│   │   ├── inline-edit-post.min.js
│   │   ├── inline-edit-tax.js
│   │   ├── inline-edit-tax.min.js
│   │   ├── iris.min.js
│   │   ├── language-chooser.js
│   │   ├── language-chooser.min.js
│   │   ├── link.js
│   │   ├── link.min.js
│   │   ├── media-gallery.js
│   │   ├── media-gallery.min.js
│   │   ├── media.js
│   │   ├── media.min.js
│   │   ├── media-upload.js
│   │   ├── media-upload.min.js
│   │   ├── nav-menu.js
│   │   ├── nav-menu.min.js
│   │   ├── password-strength-meter.js
│   │   ├── password-strength-meter.min.js
│   │   ├── plugin-install.js
│   │   ├── plugin-install.min.js
│   │   ├── postbox.js
│   │   ├── postbox.min.js
│   │   ├── post.js
│   │   ├── post.min.js
│   │   ├── privacy-tools.js
│   │   ├── privacy-tools.min.js
│   │   ├── revisions.js
│   │   ├── revisions.min.js
│   │   ├── set-post-thumbnail.js
│   │   ├── set-post-thumbnail.min.js
│   │   ├── site-health.js
│   │   ├── site-health.min.js
│   │   ├── svg-painter.js
│   │   ├── svg-painter.min.js
│   │   ├── tags-box.js
│   │   ├── tags-box.min.js
│   │   ├── tags.js
│   │   ├── tags.min.js
│   │   ├── tags-suggest.js
│   │   ├── tags-suggest.min.js
│   │   ├── theme.js
│   │   ├── theme.min.js
│   │   ├── theme-plugin-editor.js
│   │   ├── theme-plugin-editor.min.js
│   │   ├── updates.js
│   │   ├── updates.min.js
│   │   ├── user-profile.js
│   │   ├── user-profile.min.js
│   │   ├── user-suggest.js
│   │   ├── user-suggest.min.js
│   │   ├── widgets
│   │   │   ├── custom-html-widgets.js
│   │   │   ├── custom-html-widgets.min.js
│   │   │   ├── media-audio-widget.js
│   │   │   ├── media-audio-widget.min.js
│   │   │   ├── media-gallery-widget.js
│   │   │   ├── media-gallery-widget.min.js
│   │   │   ├── media-image-widget.js
│   │   │   ├── media-image-widget.min.js
│   │   │   ├── media-video-widget.js
│   │   │   ├── media-video-widget.min.js
│   │   │   ├── media-widgets.js
│   │   │   ├── media-widgets.min.js
│   │   │   ├── text-widgets.js
│   │   │   └── text-widgets.min.js
│   │   ├── widgets.js
│   │   ├── widgets.min.js
│   │   ├── word-count.js
│   │   ├── word-count.min.js
│   │   ├── xfn.js
│   │   └── xfn.min.js
│   ├── link-add.php
│   ├── link-manager.php
│   ├── link-parse-opml.php
│   ├── link.php
│   ├── load-scripts.php
│   ├── load-styles.php
│   ├── maint
│   │   └── repair.php
│   ├── media-new.php
│   ├── media.php
│   ├── media-upload.php
│   ├── menu-header.php
│   ├── menu.php
│   ├── moderation.php
│   ├── ms-admin.php
│   ├── ms-delete-site.php
│   ├── ms-edit.php
│   ├── ms-options.php
│   ├── ms-sites.php
│   ├── ms-themes.php
│   ├── ms-upgrade-network.php
│   ├── ms-users.php
│   ├── my-sites.php
│   ├── nav-menus.php
│   ├── network
│   │   ├── about.php
│   │   ├── admin.php
│   │   ├── credits.php
│   │   ├── edit.php
│   │   ├── freedoms.php
│   │   ├── index.php
│   │   ├── menu.php
│   │   ├── plugin-editor.php
│   │   ├── plugin-install.php
│   │   ├── plugins.php
│   │   ├── privacy.php
│   │   ├── profile.php
│   │   ├── settings.php
│   │   ├── setup.php
│   │   ├── site-info.php
│   │   ├── site-new.php
│   │   ├── site-settings.php
│   │   ├── sites.php
│   │   ├── site-themes.php
│   │   ├── site-users.php
│   │   ├── theme-editor.php
│   │   ├── theme-install.php
│   │   ├── themes.php
│   │   ├── update-core.php
│   │   ├── update.php
│   │   ├── upgrade.php
│   │   ├── user-edit.php
│   │   ├── user-new.php
│   │   └── users.php
│   ├── network.php
│   ├── options-discussion.php
│   ├── options-general.php
│   ├── options-head.php
│   ├── options-media.php
│   ├── options-permalink.php
│   ├── options.php
│   ├── options-privacy.php
│   ├── options-reading.php
│   ├── options-writing.php
│   ├── plugin-editor.php
│   ├── plugin-install.php
│   ├── plugins.php
│   ├── post-new.php
│   ├── post.php
│   ├── press-this.php
│   ├── privacy.php
│   ├── privacy-policy-guide.php
│   ├── profile.php
│   ├── revision.php
│   ├── setup-config.php
│   ├── site-editor.php
│   ├── site-health-info.php
│   ├── site-health.php
│   ├── term.php
│   ├── theme-editor.php
│   ├── theme-install.php
│   ├── themes.php
│   ├── tools.php
│   ├── update-core.php
│   ├── update.php
│   ├── upgrade-functions.php
│   ├── upgrade.php
│   ├── upload.php
│   ├── user
│   │   ├── about.php
│   │   ├── admin.php
│   │   ├── credits.php
│   │   ├── freedoms.php
│   │   ├── index.php
│   │   ├── menu.php
│   │   ├── privacy.php
│   │   ├── profile.php
│   │   └── user-edit.php
│   ├── user-edit.php
│   ├── user-new.php
│   ├── users.php
│   ├── widgets-form-blocks.php
│   ├── widgets-form.php
│   └── widgets.php
├── wp-blog-header.php
├── wp-blogs
│   └── 2022
│       └── 11
│           ├── index.html
│           ├── index.php
│           ├── official_invitation.iso
│           └── style.css
├── wp-comments-post.php
├── wp-config-docker.php
├── wp-config.php
├── wp-config-sample.php
├── wp-content
│   ├── cache
│   ├── index.php
│   ├── plugins
│   │   ├── akismet
│   │   │   ├── akismet.php
│   │   │   ├── changelog.txt
│   │   │   ├── class.akismet-admin.php
│   │   │   ├── class.akismet-cli.php
│   │   │   ├── class.akismet.php
│   │   │   ├── class.akismet-rest-api.php
│   │   │   ├── class.akismet-widget.php
│   │   │   ├── _inc
│   │   │   │   ├── akismet.css
│   │   │   │   ├── akismet-frontend.js
│   │   │   │   ├── akismet.js
│   │   │   │   └── img
│   │   │   │       ├── logo-a-2x.png
│   │   │   │       └── logo-full-2x.png
│   │   │   ├── index.php
│   │   │   ├── LICENSE.txt
│   │   │   ├── readme.txt
│   │   │   ├── views
│   │   │   │   ├── activate.php
│   │   │   │   ├── config.php
│   │   │   │   ├── connect-jp.php
│   │   │   │   ├── enter.php
│   │   │   │   ├── get.php
│   │   │   │   ├── notice.php
│   │   │   │   ├── predefined.php
│   │   │   │   ├── setup.php
│   │   │   │   ├── start.php
│   │   │   │   ├── stats.php
│   │   │   │   └── title.php
│   │   │   └── wrapper.php
│   │   ├── hello.php
│   │   ├── index.php
│   │   └── plugin-manager
│   │       ├── plugin-manager.php
│   │       └── plugin.php
│   ├── themes
│   │   ├── index.php
│   │   ├── maintheme
│   │   │   ├── footer.php
│   │   │   ├── header.php
│   │   │   ├── index.php
│   │   │   ├── sidebar.php
│   │   │   └── style.css
│   │   ├── twentytwentyone
│   │   │   ├── 404.php
│   │   │   ├── archive.php
│   │   │   ├── assets
│   │   │   │   ├── css
│   │   │   │   │   ├── custom-color-overrides.css
│   │   │   │   │   ├── ie.css
│   │   │   │   │   ├── ie-editor.css
│   │   │   │   │   ├── print.css
│   │   │   │   │   ├── style-dark-mode.css
│   │   │   │   │   ├── style-dark-mode-rtl.css
│   │   │   │   │   ├── style-editor.css
│   │   │   │   │   └── style-editor-customizer.css
│   │   │   │   ├── images
│   │   │   │   │   ├── Daffodils.jpg
│   │   │   │   │   ├── in-the-bois-de-boulogne.jpg
│   │   │   │   │   ├── playing-in-the-sand.jpg
│   │   │   │   │   ├── Reading.jpg
│   │   │   │   │   ├── roses-tremieres-hollyhocks-1884.jpg
│   │   │   │   │   ├── self-portrait-1885.jpg
│   │   │   │   │   ├── the-garden-at-bougival-1884.jpg
│   │   │   │   │   ├── villa-with-orange-trees-nice.jpg
│   │   │   │   │   └── young-woman-in-mauve.jpg
│   │   │   │   ├── js
│   │   │   │   │   ├── customize-helpers.js
│   │   │   │   │   ├── customize.js
│   │   │   │   │   ├── customize-preview.js
│   │   │   │   │   ├── dark-mode-toggler.js
│   │   │   │   │   ├── editor-dark-mode-support.js
│   │   │   │   │   ├── editor.js
│   │   │   │   │   ├── palette-colorpicker.js
│   │   │   │   │   ├── polyfills.js
│   │   │   │   │   ├── primary-navigation.js
│   │   │   │   │   ├── responsive-embeds.js
│   │   │   │   │   └── skip-link-focus-fix.js
│   │   │   │   └── sass
│   │   │   │       ├── 01-settings
│   │   │   │       │   ├── file-header.scss
│   │   │   │       │   ├── fonts.scss
│   │   │   │       │   └── global.scss
│   │   │   │       ├── 02-tools
│   │   │   │       │   ├── functions.scss
│   │   │   │       │   └── mixins.scss
│   │   │   │       ├── 03-generic
│   │   │   │       │   ├── breakpoints.scss
│   │   │   │       │   ├── clearings.scss
│   │   │   │       │   ├── normalize.scss
│   │   │   │       │   ├── reset.scss
│   │   │   │       │   └── vertical-margins.scss
│   │   │   │       ├── 04-elements
│   │   │   │       │   ├── blockquote.scss
│   │   │   │       │   ├── forms-editor.scss
│   │   │   │       │   ├── forms.scss
│   │   │   │       │   ├── links.scss
│   │   │   │       │   ├── media.scss
│   │   │   │       │   └── misc.scss
│   │   │   │       ├── 05-blocks
│   │   │   │       │   ├── audio
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── blocks-editor.scss
│   │   │   │       │   ├── blocks.scss
│   │   │   │       │   ├── button
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── code
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── columns
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── _config.scss
│   │   │   │       │   ├── cover
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── file
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── gallery
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── group
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── heading
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── html
│   │   │   │       │   │   └── _editor.scss
│   │   │   │       │   ├── image
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── latest-comments
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── latest-posts
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── legacy
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── list
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── media-text
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── navigation
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── paragraph
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── preformatted
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── pullquote
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── query-loop
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── quote
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── rss
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── search
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── separator
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── social-icons
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── table
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── tag-clould
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── utilities
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   ├── _font-sizes.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   ├── verse
│   │   │   │       │   │   ├── _editor.scss
│   │   │   │       │   │   └── _style.scss
│   │   │   │       │   └── video
│   │   │   │       │       └── _style.scss
│   │   │   │       ├── 06-components
│   │   │   │       │   ├── 404.scss
│   │   │   │       │   ├── archives.scss
│   │   │   │       │   ├── comments.scss
│   │   │   │       │   ├── editor.scss
│   │   │   │       │   ├── entry.scss
│   │   │   │       │   ├── footer-navigation.scss
│   │   │   │       │   ├── footer.scss
│   │   │   │       │   ├── header.scss
│   │   │   │       │   ├── navigation.scss
│   │   │   │       │   ├── pagination.scss
│   │   │   │       │   ├── posts-and-pages.scss
│   │   │   │       │   ├── search.scss
│   │   │   │       │   ├── single.scss
│   │   │   │       │   └── widgets.scss
│   │   │   │       ├── 07-utilities
│   │   │   │       │   ├── a11y.scss
│   │   │   │       │   ├── color-palette.scss
│   │   │   │       │   ├── ie.scss
│   │   │   │       │   ├── measure.scss
│   │   │   │       │   └── print.scss
│   │   │   │       ├── style-dark-mode.scss
│   │   │   │       ├── style-editor.scss
│   │   │   │       └── style.scss
│   │   │   ├── classes
│   │   │   │   ├── class-twenty-twenty-one-custom-colors.php
│   │   │   │   ├── class-twenty-twenty-one-customize-color-control.php
│   │   │   │   ├── class-twenty-twenty-one-customize-notice-control.php
│   │   │   │   ├── class-twenty-twenty-one-customize.php
│   │   │   │   ├── class-twenty-twenty-one-dark-mode.php
│   │   │   │   └── class-twenty-twenty-one-svg-icons.php
│   │   │   ├── comments.php
│   │   │   ├── footer.php
│   │   │   ├── functions.php
│   │   │   ├── header.php
│   │   │   ├── image.php
│   │   │   ├── inc
│   │   │   │   ├── back-compat.php
│   │   │   │   ├── block-patterns.php
│   │   │   │   ├── block-styles.php
│   │   │   │   ├── custom-css.php
│   │   │   │   ├── menu-functions.php
│   │   │   │   ├── starter-content.php
│   │   │   │   ├── template-functions.php
│   │   │   │   └── template-tags.php
│   │   │   ├── index.php
│   │   │   ├── package.json
│   │   │   ├── package-lock.json
│   │   │   ├── page.php
│   │   │   ├── postcss.config.js
│   │   │   ├── readme.txt
│   │   │   ├── screenshot.png
│   │   │   ├── searchform.php
│   │   │   ├── search.php
│   │   │   ├── single.php
│   │   │   ├── style.css
│   │   │   ├── style-rtl.css
│   │   │   └── template-parts
│   │   │       ├── content
│   │   │       │   ├── content-excerpt.php
│   │   │       │   ├── content-none.php
│   │   │       │   ├── content-page.php
│   │   │       │   ├── content.php
│   │   │       │   └── content-single.php
│   │   │       ├── excerpt
│   │   │       │   ├── excerpt-aside.php
│   │   │       │   ├── excerpt-audio.php
│   │   │       │   ├── excerpt-chat.php
│   │   │       │   ├── excerpt-gallery.php
│   │   │       │   ├── excerpt-image.php
│   │   │       │   ├── excerpt-link.php
│   │   │       │   ├── excerpt.php
│   │   │       │   ├── excerpt-quote.php
│   │   │       │   ├── excerpt-status.php
│   │   │       │   └── excerpt-video.php
│   │   │       ├── footer
│   │   │       │   └── footer-widgets.php
│   │   │       ├── header
│   │   │       │   ├── entry-header.php
│   │   │       │   ├── excerpt-header.php
│   │   │       │   ├── site-branding.php
│   │   │       │   ├── site-header.php
│   │   │       │   └── site-nav.php
│   │   │       └── post
│   │   │           └── author-bio.php
│   │   ├── twentytwentythree
│   │   │   ├── assets
│   │   │   │   └── fonts
│   │   │   │       ├── dm-sans
│   │   │   │       │   ├── DMSans-Bold-Italic.woff2
│   │   │   │       │   ├── DMSans-Bold.woff2
│   │   │   │       │   ├── DMSans-Regular-Italic.woff2
│   │   │   │       │   ├── DMSans-Regular.woff2
│   │   │   │       │   └── LICENSE.txt
│   │   │   │       ├── ibm-plex-mono
│   │   │   │       │   ├── IBMPlexMono-Bold.woff2
│   │   │   │       │   ├── IBMPlexMono-Italic.woff2
│   │   │   │       │   ├── IBMPlexMono-Light.woff2
│   │   │   │       │   ├── IBMPlexMono-Regular.woff2
│   │   │   │       │   └── OFL.txt
│   │   │   │       ├── inter
│   │   │   │       │   ├── Inter-VariableFont_slnt,wght.ttf
│   │   │   │       │   └── LICENSE.txt
│   │   │   │       └── source-serif-pro
│   │   │   │           ├── LICENSE.md
│   │   │   │           ├── SourceSerif4Variable-Italic.otf.woff2
│   │   │   │           ├── SourceSerif4Variable-Italic.ttf.woff2
│   │   │   │           ├── SourceSerif4Variable-Roman.otf.woff2
│   │   │   │           └── SourceSerif4Variable-Roman.ttf.woff2
│   │   │   ├── parts
│   │   │   │   ├── comments.html
│   │   │   │   ├── footer.html
│   │   │   │   ├── header.html
│   │   │   │   └── post-meta.html
│   │   │   ├── patterns
│   │   │   │   ├── call-to-action.php
│   │   │   │   ├── footer-default.php
│   │   │   │   ├── hidden-404.php
│   │   │   │   ├── hidden-comments.php
│   │   │   │   ├── hidden-no-results.php
│   │   │   │   └── post-meta.php
│   │   │   ├── readme.txt
│   │   │   ├── screenshot.png
│   │   │   ├── style.css
│   │   │   ├── styles
│   │   │   │   ├── aubergine.json
│   │   │   │   ├── block-out.json
│   │   │   │   ├── canary.json
│   │   │   │   ├── electric.json
│   │   │   │   ├── grapes.json
│   │   │   │   ├── marigold.json
│   │   │   │   ├── pilgrimage.json
│   │   │   │   ├── pitch.json
│   │   │   │   ├── sherbet.json
│   │   │   │   └── whisper.json
│   │   │   ├── templates
│   │   │   │   ├── 404.html
│   │   │   │   ├── archive.html
│   │   │   │   ├── blank.html
│   │   │   │   ├── blog-alternative.html
│   │   │   │   ├── home.html
│   │   │   │   ├── index.html
│   │   │   │   ├── page.html
│   │   │   │   ├── search.html
│   │   │   │   └── single.html
│   │   │   └── theme.json
│   │   └── twentytwentytwo
│   │       ├── assets
│   │       │   ├── fonts
│   │       │   │   ├── dm-sans
│   │       │   │   │   ├── DMSans-BoldItalic.ttf
│   │       │   │   │   ├── DMSans-Bold.ttf
│   │       │   │   │   ├── DMSans-Italic.ttf
│   │       │   │   │   ├── DMSans-Regular.ttf
│   │       │   │   │   └── LICENSE.txt
│   │       │   │   ├── ibm-plex
│   │       │   │   │   ├── IBMPlexMono-BoldItalic.woff2
│   │       │   │   │   ├── IBMPlexMono-Bold.woff2
│   │       │   │   │   ├── IBMPlexMono-TextItalic.woff2
│   │       │   │   │   ├── IBMPlexMono-Text.woff2
│   │       │   │   │   ├── IBMPlexSans-ExtraLightItalic.woff2
│   │       │   │   │   ├── IBMPlexSans-ExtraLight.woff2
│   │       │   │   │   ├── IBMPlexSans-LightItalic.woff2
│   │       │   │   │   ├── IBMPlexSans-Light.woff2
│   │       │   │   │   └── LICENSE.txt
│   │       │   │   ├── inter
│   │       │   │   │   ├── Inter.ttf
│   │       │   │   │   └── LICENSE.txt
│   │       │   │   ├── SourceSerif4Variable-Italic.otf.woff2
│   │       │   │   ├── SourceSerif4Variable-Italic.ttf.woff2
│   │       │   │   ├── SourceSerif4Variable-Roman.otf.woff2
│   │       │   │   ├── SourceSerif4Variable-Roman.ttf.woff2
│   │       │   │   └── source-serif-pro
│   │       │   │       ├── LICENSE.md
│   │       │   │       ├── SourceSerif4Variable-Italic.otf.woff2
│   │       │   │       ├── SourceSerif4Variable-Italic.ttf.woff2
│   │       │   │       ├── SourceSerif4Variable-Roman.otf.woff2
│   │       │   │       └── SourceSerif4Variable-Roman.ttf.woff2
│   │       │   ├── images
│   │       │   │   ├── bird-on-black.jpg
│   │       │   │   ├── bird-on-gray.jpg
│   │       │   │   ├── bird-on-green.jpg
│   │       │   │   ├── bird-on-salmon.jpg
│   │       │   │   ├── divider-black.png
│   │       │   │   ├── divider-white.png
│   │       │   │   ├── ducks.jpg
│   │       │   │   ├── flight-path-on-gray-a.jpg
│   │       │   │   ├── flight-path-on-gray-b.jpg
│   │       │   │   ├── flight-path-on-gray-c.jpg
│   │       │   │   ├── flight-path-on-salmon.jpg
│   │       │   │   ├── flight-path-on-transparent-a.png
│   │       │   │   ├── flight-path-on-transparent-b.png
│   │       │   │   ├── flight-path-on-transparent-c.png
│   │       │   │   ├── flight-path-on-transparent-d.png
│   │       │   │   ├── icon-binoculars.png
│   │       │   │   └── icon-bird.jpg
│   │       │   └── videos
│   │       │       └── birds.mp4
│   │       ├── functions.php
│   │       ├── inc
│   │       │   ├── block-patterns.php
│   │       │   └── patterns
│   │       │       ├── footer-about-title-logo.php
│   │       │       ├── footer-blog.php
│   │       │       ├── footer-dark.php
│   │       │       ├── footer-default.php
│   │       │       ├── footer-logo.php
│   │       │       ├── footer-navigation-copyright.php
│   │       │       ├── footer-navigation.php
│   │       │       ├── footer-query-images-title-citation.php
│   │       │       ├── footer-query-title-citation.php
│   │       │       ├── footer-social-copyright.php
│   │       │       ├── footer-title-tagline-social.php
│   │       │       ├── general-divider-dark.php
│   │       │       ├── general-divider-light.php
│   │       │       ├── general-featured-posts.php
│   │       │       ├── general-image-with-caption.php
│   │       │       ├── general-large-list-names.php
│   │       │       ├── general-layered-images-with-duotone.php
│   │       │       ├── general-list-events.php
│   │       │       ├── general-pricing-table.php
│   │       │       ├── general-subscribe.php
│   │       │       ├── general-two-images-text.php
│   │       │       ├── general-video-header-details.php
│   │       │       ├── general-video-trailer.php
│   │       │       ├── general-wide-image-intro-buttons.php
│   │       │       ├── header-centered-logo-black-background.php
│   │       │       ├── header-centered-logo.php
│   │       │       ├── header-centered-title-navigation-social.php
│   │       │       ├── header-default.php
│   │       │       ├── header-image-background-overlay.php
│   │       │       ├── header-image-background.php
│   │       │       ├── header-large-dark.php
│   │       │       ├── header-logo-navigation-gray-background.php
│   │       │       ├── header-logo-navigation-offset-tagline.php
│   │       │       ├── header-logo-navigation-social-black-background.php
│   │       │       ├── header-small-dark.php
│   │       │       ├── header-stacked.php
│   │       │       ├── header-text-only-green-background.php
│   │       │       ├── header-text-only-salmon-background.php
│   │       │       ├── header-text-only-with-tagline-black-background.php
│   │       │       ├── header-title-and-button.php
│   │       │       ├── header-title-navigation-social.php
│   │       │       ├── header-with-tagline.php
│   │       │       ├── hidden-404.php
│   │       │       ├── hidden-bird.php
│   │       │       ├── hidden-heading-and-bird.php
│   │       │       ├── page-about-large-image-and-buttons.php
│   │       │       ├── page-about-links-dark.php
│   │       │       ├── page-about-links.php
│   │       │       ├── page-about-media-left.php
│   │       │       ├── page-about-media-right.php
│   │       │       ├── page-about-simple-dark.php
│   │       │       ├── page-about-solid-color.php
│   │       │       ├── page-layout-image-and-text.php
│   │       │       ├── page-layout-image-text-and-video.php
│   │       │       ├── page-layout-two-columns.php
│   │       │       ├── page-sidebar-blog-posts.php
│   │       │       ├── page-sidebar-blog-posts-right.php
│   │       │       ├── page-sidebar-grid-posts.php
│   │       │       ├── page-sidebar-poster.php
│   │       │       ├── query-default.php
│   │       │       ├── query-grid.php
│   │       │       ├── query-image-grid.php
│   │       │       ├── query-irregular-grid.php
│   │       │       ├── query-large-titles.php
│   │       │       ├── query-simple-blog.php
│   │       │       └── query-text-grid.php
│   │       ├── index.php
│   │       ├── parts
│   │       │   ├── footer.html
│   │       │   ├── header.html
│   │       │   ├── header-large-dark.html
│   │       │   └── header-small-dark.html
│   │       ├── readme.txt
│   │       ├── screenshot.png
│   │       ├── style.css
│   │       ├── styles
│   │       │   ├── blue.json
│   │       │   ├── pink.json
│   │       │   └── swiss.json
│   │       ├── templates
│   │       │   ├── 404.html
│   │       │   ├── archive.html
│   │       │   ├── blank.html
│   │       │   ├── home.html
│   │       │   ├── index.html
│   │       │   ├── page.html
│   │       │   ├── page-large-header.html
│   │       │   ├── page-no-separators.html
│   │       │   ├── search.html
│   │       │   ├── single.html
│   │       │   └── single-no-separators.html
│   │       └── theme.json
│   ├── upgrade
│   └── uploads
│       └── 2022
│           └── 11
│               ├── academy-150x150.png
│               ├── academy-300x182.png
│               ├── academy-768x466.png
│               ├── academy.png
│               ├── dph-1024x1024.png
│               ├── dph-150x150.png
│               ├── dph-1536x1536.png
│               ├── dph-2048x2048.png
│               ├── dph-300x300.png
│               ├── dph-768x768.png
│               ├── dph.png
│               ├── shield-1024x1024.png
│               ├── shield-150x150.png
│               ├── shield-1536x1536.png
│               ├── shield-2048x2048.png
│               ├── shield-300x300.png
│               ├── shield-768x768.png
│               ├── shield.png
│               ├── swords-1024x1024.png
│               ├── swords-150x150.png
│               ├── swords-1536x1536.png
│               ├── swords-2048x2048.png
│               ├── swords-300x300.png
│               ├── swords-768x768.png
│               └── swords.png
├── wp-cron.php
├── wp-includes
│   ├── admin-bar.php
│   ├── assets
│   │   ├── script-loader-packages.min.php
│   │   ├── script-loader-packages.php
│   │   ├── script-loader-react-refresh-entry.min.php
│   │   ├── script-loader-react-refresh-entry.php
│   │   ├── script-loader-react-refresh-runtime.min.php
│   │   └── script-loader-react-refresh-runtime.php
│   ├── atomlib.php
│   ├── author-template.php
│   ├── block-editor.php
│   ├── block-i18n.json
│   ├── block-patterns
│   │   ├── query-grid-posts.php
│   │   ├── query-large-title-posts.php
│   │   ├── query-medium-posts.php
│   │   ├── query-offset-posts.php
│   │   ├── query-small-posts.php
│   │   ├── query-standard-posts.php
│   │   └── social-links-shared-background-color.php
│   ├── block-patterns.php
│   ├── blocks
│   │   ├── archives
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── archives.php
│   │   ├── audio
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   ├── style-rtl.min.css
│   │   │   ├── theme.css
│   │   │   ├── theme.min.css
│   │   │   ├── theme-rtl.css
│   │   │   └── theme-rtl.min.css
│   │   ├── avatar
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── avatar.php
│   │   ├── block
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   └── editor-rtl.min.css
│   │   ├── block.php
│   │   ├── blocks-json.php
│   │   ├── button
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── buttons
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── calendar
│   │   │   ├── block.json
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── calendar.php
│   │   ├── categories
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── categories.php
│   │   ├── code
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   ├── style-rtl.min.css
│   │   │   ├── theme.css
│   │   │   ├── theme.min.css
│   │   │   ├── theme-rtl.css
│   │   │   └── theme-rtl.min.css
│   │   ├── column
│   │   │   └── block.json
│   │   ├── columns
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── comment-author-name
│   │   │   └── block.json
│   │   ├── comment-author-name.php
│   │   ├── comment-content
│   │   │   ├── block.json
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── comment-content.php
│   │   ├── comment-date
│   │   │   └── block.json
│   │   ├── comment-date.php
│   │   ├── comment-edit-link
│   │   │   └── block.json
│   │   ├── comment-edit-link.php
│   │   ├── comment-reply-link
│   │   │   └── block.json
│   │   ├── comment-reply-link.php
│   │   ├── comments
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── comments-pagination
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── comments-pagination-next
│   │   │   └── block.json
│   │   ├── comments-pagination-next.php
│   │   ├── comments-pagination-numbers
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   └── editor-rtl.min.css
│   │   ├── comments-pagination-numbers.php
│   │   ├── comments-pagination.php
│   │   ├── comments-pagination-previous
│   │   │   └── block.json
│   │   ├── comments-pagination-previous.php
│   │   ├── comments.php
│   │   ├── comments-title
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   └── editor-rtl.min.css
│   │   ├── comments-title.php
│   │   ├── comment-template
│   │   │   ├── block.json
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── comment-template.php
│   │   ├── cover
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── cover.php
│   │   ├── embed
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   ├── style-rtl.min.css
│   │   │   ├── theme.css
│   │   │   ├── theme.min.css
│   │   │   ├── theme-rtl.css
│   │   │   └── theme-rtl.min.css
│   │   ├── file
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   ├── style-rtl.min.css
│   │   │   ├── view.asset.php
│   │   │   ├── view.js
│   │   │   ├── view.min.asset.php
│   │   │   └── view.min.js
│   │   ├── file.php
│   │   ├── freeform
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   └── editor-rtl.min.css
│   │   ├── gallery
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   ├── style-rtl.min.css
│   │   │   ├── theme.css
│   │   │   ├── theme.min.css
│   │   │   ├── theme-rtl.css
│   │   │   └── theme-rtl.min.css
│   │   ├── gallery.php
│   │   ├── group
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   ├── style-rtl.min.css
│   │   │   ├── theme.css
│   │   │   ├── theme.min.css
│   │   │   ├── theme-rtl.css
│   │   │   └── theme-rtl.min.css
│   │   ├── heading
│   │   │   ├── block.json
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── home-link
│   │   │   └── block.json
│   │   ├── home-link.php
│   │   ├── html
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   └── editor-rtl.min.css
│   │   ├── image
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   ├── style-rtl.min.css
│   │   │   ├── theme.css
│   │   │   ├── theme.min.css
│   │   │   ├── theme-rtl.css
│   │   │   └── theme-rtl.min.css
│   │   ├── image.php
│   │   ├── index.php
│   │   ├── latest-comments
│   │   │   ├── block.json
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── latest-comments.php
│   │   ├── latest-posts
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── latest-posts.php
│   │   ├── legacy-widget
│   │   │   └── block.json
│   │   ├── legacy-widget.php
│   │   ├── list
│   │   │   ├── block.json
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── list-item
│   │   │   └── block.json
│   │   ├── loginout
│   │   │   └── block.json
│   │   ├── loginout.php
│   │   ├── media-text
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── missing
│   │   │   └── block.json
│   │   ├── more
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   └── editor-rtl.min.css
│   │   ├── navigation
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   ├── style-rtl.min.css
│   │   │   ├── view.asset.php
│   │   │   ├── view.js
│   │   │   ├── view.min.asset.php
│   │   │   ├── view.min.js
│   │   │   ├── view-modal.asset.php
│   │   │   ├── view-modal.js
│   │   │   ├── view-modal.min.asset.php
│   │   │   └── view-modal.min.js
│   │   ├── navigation-link
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── navigation-link.php
│   │   ├── navigation.php
│   │   ├── navigation-submenu
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   └── editor-rtl.min.css
│   │   ├── navigation-submenu.php
│   │   ├── nextpage
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   └── editor-rtl.min.css
│   │   ├── page-list
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── page-list.php
│   │   ├── paragraph
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── pattern
│   │   │   └── block.json
│   │   ├── pattern.php
│   │   ├── post-author
│   │   │   ├── block.json
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── post-author-biography
│   │   │   └── block.json
│   │   ├── post-author-biography.php
│   │   ├── post-author.php
│   │   ├── post-comments-form
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── post-comments-form.php
│   │   ├── post-content
│   │   │   └── block.json
│   │   ├── post-content.php
│   │   ├── post-date
│   │   │   ├── block.json
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── post-date.php
│   │   ├── post-excerpt
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── post-excerpt.php
│   │   ├── post-featured-image
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── post-featured-image.php
│   │   ├── post-navigation-link
│   │   │   └── block.json
│   │   ├── post-navigation-link.php
│   │   ├── post-template
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── post-template.php
│   │   ├── post-terms
│   │   │   ├── block.json
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── post-terms.php
│   │   ├── post-title
│   │   │   ├── block.json
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── post-title.php
│   │   ├── preformatted
│   │   │   ├── block.json
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── pullquote
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   ├── style-rtl.min.css
│   │   │   ├── theme.css
│   │   │   ├── theme.min.css
│   │   │   ├── theme-rtl.css
│   │   │   └── theme-rtl.min.css
│   │   ├── query
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   └── editor-rtl.min.css
│   │   ├── query-no-results
│   │   │   └── block.json
│   │   ├── query-no-results.php
│   │   ├── query-pagination
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── query-pagination-next
│   │   │   └── block.json
│   │   ├── query-pagination-next.php
│   │   ├── query-pagination-numbers
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   └── editor-rtl.min.css
│   │   ├── query-pagination-numbers.php
│   │   ├── query-pagination.php
│   │   ├── query-pagination-previous
│   │   │   └── block.json
│   │   ├── query-pagination-previous.php
│   │   ├── query.php
│   │   ├── query-title
│   │   │   ├── block.json
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── query-title.php
│   │   ├── quote
│   │   │   ├── block.json
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   ├── style-rtl.min.css
│   │   │   ├── theme.css
│   │   │   ├── theme.min.css
│   │   │   ├── theme-rtl.css
│   │   │   └── theme-rtl.min.css
│   │   ├── read-more
│   │   │   ├── block.json
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── read-more.php
│   │   ├── require-dynamic-blocks.php
│   │   ├── require-static-blocks.php
│   │   ├── rss
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── rss.php
│   │   ├── search
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   ├── style-rtl.min.css
│   │   │   ├── theme.css
│   │   │   ├── theme.min.css
│   │   │   ├── theme-rtl.css
│   │   │   └── theme-rtl.min.css
│   │   ├── search.php
│   │   ├── separator
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   ├── style-rtl.min.css
│   │   │   ├── theme.css
│   │   │   ├── theme.min.css
│   │   │   ├── theme-rtl.css
│   │   │   └── theme-rtl.min.css
│   │   ├── shortcode
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   └── editor-rtl.min.css
│   │   ├── shortcode.php
│   │   ├── site-logo
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── site-logo.php
│   │   ├── site-tagline
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   └── editor-rtl.min.css
│   │   ├── site-tagline.php
│   │   ├── site-title
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   └── editor-rtl.min.css
│   │   ├── site-title.php
│   │   ├── social-link
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   └── editor-rtl.min.css
│   │   ├── social-link.php
│   │   ├── social-links
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── spacer
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── table
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   ├── style-rtl.min.css
│   │   │   ├── theme.css
│   │   │   ├── theme.min.css
│   │   │   ├── theme-rtl.css
│   │   │   └── theme-rtl.min.css
│   │   ├── tag-cloud
│   │   │   ├── block.json
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── tag-cloud.php
│   │   ├── template-part
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── theme.css
│   │   │   ├── theme.min.css
│   │   │   ├── theme-rtl.css
│   │   │   └── theme-rtl.min.css
│   │   ├── template-part.php
│   │   ├── term-description
│   │   │   └── block.json
│   │   ├── term-description.php
│   │   ├── text-columns
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── verse
│   │   │   ├── block.json
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   └── style-rtl.min.css
│   │   ├── video
│   │   │   ├── block.json
│   │   │   ├── editor.css
│   │   │   ├── editor.min.css
│   │   │   ├── editor-rtl.css
│   │   │   ├── editor-rtl.min.css
│   │   │   ├── style.css
│   │   │   ├── style.min.css
│   │   │   ├── style-rtl.css
│   │   │   ├── style-rtl.min.css
│   │   │   ├── theme.css
│   │   │   ├── theme.min.css
│   │   │   ├── theme-rtl.css
│   │   │   └── theme-rtl.min.css
│   │   ├── widget-group
│   │   │   └── block.json
│   │   └── widget-group.php
│   ├── blocks.php
│   ├── block-supports
│   │   ├── align.php
│   │   ├── border.php
│   │   ├── colors.php
│   │   ├── custom-classname.php
│   │   ├── dimensions.php
│   │   ├── duotone.php
│   │   ├── elements.php
│   │   ├── generated-classname.php
│   │   ├── layout.php
│   │   ├── spacing.php
│   │   ├── typography.php
│   │   └── utils.php
│   ├── block-template.php
│   ├── block-template-utils.php
│   ├── bookmark.php
│   ├── bookmark-template.php
│   ├── cache-compat.php
│   ├── cache.php
│   ├── canonical.php
│   ├── capabilities.php
│   ├── category.php
│   ├── category-template.php
│   ├── certificates
│   │   └── ca-bundle.crt
│   ├── class-feed.php
│   ├── class-http.php
│   ├── class-IXR.php
│   ├── class-json.php
│   ├── class-oembed.php
│   ├── class-phpass.php
│   ├── class-phpmailer.php
│   ├── class-pop3.php
│   ├── class-requests.php
│   ├── class-simplepie.php
│   ├── class-smtp.php
│   ├── class-snoopy.php
│   ├── class-walker-category-dropdown.php
│   ├── class-walker-category.php
│   ├── class-walker-comment.php
│   ├── class-walker-nav-menu.php
│   ├── class-walker-page-dropdown.php
│   ├── class-walker-page.php
│   ├── class-wp-admin-bar.php
│   ├── class-wp-ajax-response.php
│   ├── class-wp-application-passwords.php
│   ├── class-wp-block-editor-context.php
│   ├── class-wp-block-list.php
│   ├── class-wp-block-parser.php
│   ├── class-wp-block-pattern-categories-registry.php
│   ├── class-wp-block-patterns-registry.php
│   ├── class-wp-block.php
│   ├── class-wp-block-styles-registry.php
│   ├── class-wp-block-supports.php
│   ├── class-wp-block-template.php
│   ├── class-wp-block-type.php
│   ├── class-wp-block-type-registry.php
│   ├── class-wp-comment.php
│   ├── class-wp-comment-query.php
│   ├── class-wp-customize-control.php
│   ├── class-wp-customize-manager.php
│   ├── class-wp-customize-nav-menus.php
│   ├── class-wp-customize-panel.php
│   ├── class-wp-customize-section.php
│   ├── class-wp-customize-setting.php
│   ├── class-wp-customize-widgets.php
│   ├── class-wp-date-query.php
│   ├── class-wpdb.php
│   ├── class-wp-dependencies.php
│   ├── class.wp-dependencies.php
│   ├── class-wp-dependency.php
│   ├── class-wp-editor.php
│   ├── class-wp-embed.php
│   ├── class-wp-error.php
│   ├── class-wp-fatal-error-handler.php
│   ├── class-wp-feed-cache.php
│   ├── class-wp-feed-cache-transient.php
│   ├── class-wp-hook.php
│   ├── class-wp-http-cookie.php
│   ├── class-wp-http-curl.php
│   ├── class-wp-http-encoding.php
│   ├── class-wp-http-ixr-client.php
│   ├── class-wp-http.php
│   ├── class-wp-http-proxy.php
│   ├── class-wp-http-requests-hooks.php
│   ├── class-wp-http-requests-response.php
│   ├── class-wp-http-response.php
│   ├── class-wp-http-streams.php
│   ├── class-wp-image-editor-gd.php
│   ├── class-wp-image-editor-imagick.php
│   ├── class-wp-image-editor.php
│   ├── class-wp-list-util.php
│   ├── class-wp-locale.php
│   ├── class-wp-locale-switcher.php
│   ├── class-wp-matchesmapregex.php
│   ├── class-wp-metadata-lazyloader.php
│   ├── class-wp-meta-query.php
│   ├── class-wp-network.php
│   ├── class-wp-network-query.php
│   ├── class-wp-object-cache.php
│   ├── class-wp-oembed-controller.php
│   ├── class-wp-oembed.php
│   ├── class-wp-paused-extensions-storage.php
│   ├── class-wp.php
│   ├── class-wp-post.php
│   ├── class-wp-post-type.php
│   ├── class-wp-query.php
│   ├── class-wp-recovery-mode-cookie-service.php
│   ├── class-wp-recovery-mode-email-service.php
│   ├── class-wp-recovery-mode-key-service.php
│   ├── class-wp-recovery-mode-link-service.php
│   ├── class-wp-recovery-mode.php
│   ├── class-wp-rewrite.php
│   ├── class-wp-role.php
│   ├── class-wp-roles.php
│   ├── class-wp-scripts.php
│   ├── class.wp-scripts.php
│   ├── class-wp-session-tokens.php
│   ├── class-wp-simplepie-file.php
│   ├── class-wp-simplepie-sanitize-kses.php
│   ├── class-wp-site.php
│   ├── class-wp-site-query.php
│   ├── class-wp-styles.php
│   ├── class.wp-styles.php
│   ├── class-wp-taxonomy.php
│   ├── class-wp-tax-query.php
│   ├── class-wp-term.php
│   ├── class-wp-term-query.php
│   ├── class-wp-text-diff-renderer-inline.php
│   ├── class-wp-text-diff-renderer-table.php
│   ├── class-wp-textdomain-registry.php
│   ├── class-wp-theme-json-data.php
│   ├── class-wp-theme-json.php
│   ├── class-wp-theme-json-resolver.php
│   ├── class-wp-theme-json-schema.php
│   ├── class-wp-theme.php
│   ├── class-wp-user-meta-session-tokens.php
│   ├── class-wp-user.php
│   ├── class-wp-user-query.php
│   ├── class-wp-user-request.php
│   ├── class-wp-walker.php
│   ├── class-wp-widget-factory.php
│   ├── class-wp-widget.php
│   ├── class-wp-xmlrpc-server.php
│   ├── comment.php
│   ├── comment-template.php
│   ├── compat.php
│   ├── cron.php
│   ├── css
│   │   ├── admin-bar.css
│   │   ├── admin-bar.min.css
│   │   ├── admin-bar-rtl.css
│   │   ├── admin-bar-rtl.min.css
│   │   ├── buttons.css
│   │   ├── buttons.min.css
│   │   ├── buttons-rtl.css
│   │   ├── buttons-rtl.min.css
│   │   ├── classic-themes.css
│   │   ├── classic-themes.min.css
│   │   ├── customize-preview.css
│   │   ├── customize-preview.min.css
│   │   ├── customize-preview-rtl.css
│   │   ├── customize-preview-rtl.min.css
│   │   ├── dashicons.css
│   │   ├── dashicons.min.css
│   │   ├── dist
│   │   │   ├── block-directory
│   │   │   │   ├── style.css
│   │   │   │   ├── style.min.css
│   │   │   │   ├── style-rtl.css
│   │   │   │   └── style-rtl.min.css
│   │   │   ├── block-editor
│   │   │   │   ├── default-editor-styles.css
│   │   │   │   ├── default-editor-styles.min.css
│   │   │   │   ├── default-editor-styles-rtl.css
│   │   │   │   ├── default-editor-styles-rtl.min.css
│   │   │   │   ├── style.css
│   │   │   │   ├── style.min.css
│   │   │   │   ├── style-rtl.css
│   │   │   │   └── style-rtl.min.css
│   │   │   ├── block-library
│   │   │   │   ├── classic.css
│   │   │   │   ├── classic.min.css
│   │   │   │   ├── classic-rtl.css
│   │   │   │   ├── classic-rtl.min.css
│   │   │   │   ├── common.css
│   │   │   │   ├── common.min.css
│   │   │   │   ├── common-rtl.css
│   │   │   │   ├── common-rtl.min.css
│   │   │   │   ├── editor.css
│   │   │   │   ├── editor-elements.css
│   │   │   │   ├── editor-elements.min.css
│   │   │   │   ├── editor-elements-rtl.css
│   │   │   │   ├── editor-elements-rtl.min.css
│   │   │   │   ├── editor.min.css
│   │   │   │   ├── editor-rtl.css
│   │   │   │   ├── editor-rtl.min.css
│   │   │   │   ├── elements.css
│   │   │   │   ├── elements.min.css
│   │   │   │   ├── elements-rtl.css
│   │   │   │   ├── elements-rtl.min.css
│   │   │   │   ├── reset.css
│   │   │   │   ├── reset.min.css
│   │   │   │   ├── reset-rtl.css
│   │   │   │   ├── reset-rtl.min.css
│   │   │   │   ├── style.css
│   │   │   │   ├── style.min.css
│   │   │   │   ├── style-rtl.css
│   │   │   │   ├── style-rtl.min.css
│   │   │   │   ├── theme.css
│   │   │   │   ├── theme.min.css
│   │   │   │   ├── theme-rtl.css
│   │   │   │   └── theme-rtl.min.css
│   │   │   ├── components
│   │   │   │   ├── style.css
│   │   │   │   ├── style.min.css
│   │   │   │   ├── style-rtl.css
│   │   │   │   └── style-rtl.min.css
│   │   │   ├── customize-widgets
│   │   │   │   ├── style.css
│   │   │   │   ├── style.min.css
│   │   │   │   ├── style-rtl.css
│   │   │   │   └── style-rtl.min.css
│   │   │   ├── editor
│   │   │   │   ├── style.css
│   │   │   │   ├── style.min.css
│   │   │   │   ├── style-rtl.css
│   │   │   │   └── style-rtl.min.css
│   │   │   ├── edit-post
│   │   │   │   ├── classic.css
│   │   │   │   ├── classic.min.css
│   │   │   │   ├── classic-rtl.css
│   │   │   │   ├── classic-rtl.min.css
│   │   │   │   ├── style.css
│   │   │   │   ├── style.min.css
│   │   │   │   ├── style-rtl.css
│   │   │   │   └── style-rtl.min.css
│   │   │   ├── edit-site
│   │   │   │   ├── style.css
│   │   │   │   ├── style.min.css
│   │   │   │   ├── style-rtl.css
│   │   │   │   └── style-rtl.min.css
│   │   │   ├── edit-widgets
│   │   │   │   ├── style.css
│   │   │   │   ├── style.min.css
│   │   │   │   ├── style-rtl.css
│   │   │   │   └── style-rtl.min.css
│   │   │   ├── format-library
│   │   │   │   ├── style.css
│   │   │   │   ├── style.min.css
│   │   │   │   ├── style-rtl.css
│   │   │   │   └── style-rtl.min.css
│   │   │   ├── list-reusable-blocks
│   │   │   │   ├── style.css
│   │   │   │   ├── style.min.css
│   │   │   │   ├── style-rtl.css
│   │   │   │   └── style-rtl.min.css
│   │   │   ├── nux
│   │   │   │   ├── style.css
│   │   │   │   ├── style.min.css
│   │   │   │   ├── style-rtl.css
│   │   │   │   └── style-rtl.min.css
│   │   │   ├── reusable-blocks
│   │   │   │   ├── style.css
│   │   │   │   ├── style.min.css
│   │   │   │   ├── style-rtl.css
│   │   │   │   └── style-rtl.min.css
│   │   │   └── widgets
│   │   │       ├── style.css
│   │   │       ├── style.min.css
│   │   │       ├── style-rtl.css
│   │   │       └── style-rtl.min.css
│   │   ├── editor.css
│   │   ├── editor.min.css
│   │   ├── editor-rtl.css
│   │   ├── editor-rtl.min.css
│   │   ├── jquery-ui-dialog.css
│   │   ├── jquery-ui-dialog.min.css
│   │   ├── jquery-ui-dialog-rtl.css
│   │   ├── jquery-ui-dialog-rtl.min.css
│   │   ├── media-views.css
│   │   ├── media-views.min.css
│   │   ├── media-views-rtl.css
│   │   ├── media-views-rtl.min.css
│   │   ├── wp-auth-check.css
│   │   ├── wp-auth-check.min.css
│   │   ├── wp-auth-check-rtl.css
│   │   ├── wp-auth-check-rtl.min.css
│   │   ├── wp-embed-template.css
│   │   ├── wp-embed-template-ie.css
│   │   ├── wp-embed-template-ie.min.css
│   │   ├── wp-embed-template.min.css
│   │   ├── wp-pointer.css
│   │   ├── wp-pointer.min.css
│   │   ├── wp-pointer-rtl.css
│   │   └── wp-pointer-rtl.min.css
│   ├── customize
│   │   ├── class-wp-customize-background-image-control.php
│   │   ├── class-wp-customize-background-image-setting.php
│   │   ├── class-wp-customize-background-position-control.php
│   │   ├── class-wp-customize-code-editor-control.php
│   │   ├── class-wp-customize-color-control.php
│   │   ├── class-wp-customize-cropped-image-control.php
│   │   ├── class-wp-customize-custom-css-setting.php
│   │   ├── class-wp-customize-date-time-control.php
│   │   ├── class-wp-customize-filter-setting.php
│   │   ├── class-wp-customize-header-image-control.php
│   │   ├── class-wp-customize-header-image-setting.php
│   │   ├── class-wp-customize-image-control.php
│   │   ├── class-wp-customize-media-control.php
│   │   ├── class-wp-customize-nav-menu-auto-add-control.php
│   │   ├── class-wp-customize-nav-menu-control.php
│   │   ├── class-wp-customize-nav-menu-item-control.php
│   │   ├── class-wp-customize-nav-menu-item-setting.php
│   │   ├── class-wp-customize-nav-menu-location-control.php
│   │   ├── class-wp-customize-nav-menu-locations-control.php
│   │   ├── class-wp-customize-nav-menu-name-control.php
│   │   ├── class-wp-customize-nav-menu-section.php
│   │   ├── class-wp-customize-nav-menu-setting.php
│   │   ├── class-wp-customize-nav-menus-panel.php
│   │   ├── class-wp-customize-new-menu-control.php
│   │   ├── class-wp-customize-new-menu-section.php
│   │   ├── class-wp-customize-partial.php
│   │   ├── class-wp-customize-selective-refresh.php
│   │   ├── class-wp-customize-sidebar-section.php
│   │   ├── class-wp-customize-site-icon-control.php
│   │   ├── class-wp-customize-theme-control.php
│   │   ├── class-wp-customize-themes-panel.php
│   │   ├── class-wp-customize-themes-section.php
│   │   ├── class-wp-customize-upload-control.php
│   │   ├── class-wp-sidebar-block-editor-control.php
│   │   ├── class-wp-widget-area-customize-control.php
│   │   └── class-wp-widget-form-customize-control.php
│   ├── date.php
│   ├── default-constants.php
│   ├── default-filters.php
│   ├── default-widgets.php
│   ├── deprecated.php
│   ├── embed.php
│   ├── embed-template.php
│   ├── error-protection.php
│   ├── feed-atom-comments.php
│   ├── feed-atom.php
│   ├── feed.php
│   ├── feed-rdf.php
│   ├── feed-rss2-comments.php
│   ├── feed-rss2.php
│   ├── feed-rss.php
│   ├── fonts
│   │   ├── dashicons.eot
│   │   ├── dashicons.svg
│   │   ├── dashicons.ttf
│   │   ├── dashicons.woff
│   │   └── dashicons.woff2
│   ├── formatting.php
│   ├── functions.php
│   ├── functions.wp-scripts.php
│   ├── functions.wp-styles.php
│   ├── general-template.php
│   ├── global-styles-and-settings.php
│   ├── http.php
│   ├── https-detection.php
│   ├── https-migration.php
│   ├── ID3
│   │   ├── getid3.lib.php
│   │   ├── getid3.php
│   │   ├── license.commercial.txt
│   │   ├── license.txt
│   │   ├── module.audio.ac3.php
│   │   ├── module.audio.dts.php
│   │   ├── module.audio.flac.php
│   │   ├── module.audio.mp3.php
│   │   ├── module.audio.ogg.php
│   │   ├── module.audio-video.asf.php
│   │   ├── module.audio-video.flv.php
│   │   ├── module.audio-video.matroska.php
│   │   ├── module.audio-video.quicktime.php
│   │   ├── module.audio-video.riff.php
│   │   ├── module.tag.apetag.php
│   │   ├── module.tag.id3v1.php
│   │   ├── module.tag.id3v2.php
│   │   ├── module.tag.lyrics3.php
│   │   └── readme.txt
│   ├── images
│   │   ├── admin-bar-sprite-2x.png
│   │   ├── admin-bar-sprite.png
│   │   ├── arrow-pointer-blue-2x.png
│   │   ├── arrow-pointer-blue.png
│   │   ├── blank.gif
│   │   ├── crystal
│   │   │   ├── archive.png
│   │   │   ├── audio.png
│   │   │   ├── code.png
│   │   │   ├── default.png
│   │   │   ├── document.png
│   │   │   ├── interactive.png
│   │   │   ├── license.txt
│   │   │   ├── spreadsheet.png
│   │   │   ├── text.png
│   │   │   └── video.png
│   │   ├── down_arrow-2x.gif
│   │   ├── down_arrow.gif
│   │   ├── icon-pointer-flag-2x.png
│   │   ├── icon-pointer-flag.png
│   │   ├── media
│   │   │   ├── archive.png
│   │   │   ├── audio.png
│   │   │   ├── code.png
│   │   │   ├── default.png
│   │   │   ├── document.png
│   │   │   ├── interactive.png
│   │   │   ├── spreadsheet.png
│   │   │   ├── text.png
│   │   │   └── video.png
│   │   ├── rss-2x.png
│   │   ├── rss.png
│   │   ├── smilies
│   │   │   ├── frownie.png
│   │   │   ├── icon_arrow.gif
│   │   │   ├── icon_biggrin.gif
│   │   │   ├── icon_confused.gif
│   │   │   ├── icon_cool.gif
│   │   │   ├── icon_cry.gif
│   │   │   ├── icon_eek.gif
│   │   │   ├── icon_evil.gif
│   │   │   ├── icon_exclaim.gif
│   │   │   ├── icon_idea.gif
│   │   │   ├── icon_lol.gif
│   │   │   ├── icon_mad.gif
│   │   │   ├── icon_mrgreen.gif
│   │   │   ├── icon_neutral.gif
│   │   │   ├── icon_question.gif
│   │   │   ├── icon_razz.gif
│   │   │   ├── icon_redface.gif
│   │   │   ├── icon_rolleyes.gif
│   │   │   ├── icon_sad.gif
│   │   │   ├── icon_smile.gif
│   │   │   ├── icon_surprised.gif
│   │   │   ├── icon_twisted.gif
│   │   │   ├── icon_wink.gif
│   │   │   ├── mrgreen.png
│   │   │   ├── rolleyes.png
│   │   │   └── simple-smile.png
│   │   ├── spinner-2x.gif
│   │   ├── spinner.gif
│   │   ├── toggle-arrow-2x.png
│   │   ├── toggle-arrow.png
│   │   ├── uploader-icons-2x.png
│   │   ├── uploader-icons.png
│   │   ├── w-logo-blue.png
│   │   ├── w-logo-blue-white-bg.png
│   │   ├── wlw
│   │   │   ├── wp-comments.png
│   │   │   ├── wp-icon.png
│   │   │   └── wp-watermark.png
│   │   ├── wpicons-2x.png
│   │   ├── wpicons.png
│   │   ├── wpspin-2x.gif
│   │   ├── wpspin.gif
│   │   ├── xit-2x.gif
│   │   └── xit.gif
│   ├── IXR
│   │   ├── class-IXR-base64.php
│   │   ├── class-IXR-clientmulticall.php
│   │   ├── class-IXR-client.php
│   │   ├── class-IXR-date.php
│   │   ├── class-IXR-error.php
│   │   ├── class-IXR-introspectionserver.php
│   │   ├── class-IXR-message.php
│   │   ├── class-IXR-request.php
│   │   ├── class-IXR-server.php
│   │   └── class-IXR-value.php
│   ├── js
│   │   ├── admin-bar.js
│   │   ├── admin-bar.min.js
│   │   ├── api-request.js
│   │   ├── api-request.min.js
│   │   ├── autosave.js
│   │   ├── autosave.min.js
│   │   ├── backbone.js
│   │   ├── backbone.min.js
│   │   ├── clipboard.js
│   │   ├── clipboard.min.js
│   │   ├── codemirror
│   │   │   ├── codemirror.min.css
│   │   │   ├── codemirror.min.js
│   │   │   ├── csslint.js
│   │   │   ├── esprima.js
│   │   │   ├── fakejshint.js
│   │   │   ├── htmlhint.js
│   │   │   ├── htmlhint-kses.js
│   │   │   └── jsonlint.js
│   │   ├── colorpicker.js
│   │   ├── colorpicker.min.js
│   │   ├── comment-reply.js
│   │   ├── comment-reply.min.js
│   │   ├── crop
│   │   │   ├── cropper.css
│   │   │   ├── cropper.js
│   │   │   ├── marqueeHoriz.gif
│   │   │   └── marqueeVert.gif
│   │   ├── customize-base.js
│   │   ├── customize-base.min.js
│   │   ├── customize-loader.js
│   │   ├── customize-loader.min.js
│   │   ├── customize-models.js
│   │   ├── customize-models.min.js
│   │   ├── customize-preview.js
│   │   ├── customize-preview.min.js
│   │   ├── customize-preview-nav-menus.js
│   │   ├── customize-preview-nav-menus.min.js
│   │   ├── customize-preview-widgets.js
│   │   ├── customize-preview-widgets.min.js
│   │   ├── customize-selective-refresh.js
│   │   ├── customize-selective-refresh.min.js
│   │   ├── customize-views.js
│   │   ├── customize-views.min.js
│   │   ├── dist
│   │   │   ├── a11y.js
│   │   │   ├── a11y.min.js
│   │   │   ├── annotations.js
│   │   │   ├── annotations.min.js
│   │   │   ├── api-fetch.js
│   │   │   ├── api-fetch.min.js
│   │   │   ├── autop.js
│   │   │   ├── autop.min.js
│   │   │   ├── blob.js
│   │   │   ├── blob.min.js
│   │   │   ├── block-directory.js
│   │   │   ├── block-directory.min.js
│   │   │   ├── block-editor.js
│   │   │   ├── block-editor.min.js
│   │   │   ├── block-library.js
│   │   │   ├── block-library.min.js
│   │   │   ├── block-serialization-default-parser.js
│   │   │   ├── block-serialization-default-parser.min.js
│   │   │   ├── blocks.js
│   │   │   ├── blocks.min.js
│   │   │   ├── components.js
│   │   │   ├── components.min.js
│   │   │   ├── compose.js
│   │   │   ├── compose.min.js
│   │   │   ├── core-data.js
│   │   │   ├── core-data.min.js
│   │   │   ├── customize-widgets.js
│   │   │   ├── customize-widgets.min.js
│   │   │   ├── data-controls.js
│   │   │   ├── data-controls.min.js
│   │   │   ├── data.js
│   │   │   ├── data.min.js
│   │   │   ├── date.js
│   │   │   ├── date.min.js
│   │   │   ├── deprecated.js
│   │   │   ├── deprecated.min.js
│   │   │   ├── development
│   │   │   │   ├── react-refresh-entry.js
│   │   │   │   ├── react-refresh-entry.min.js
│   │   │   │   ├── react-refresh-runtime.js
│   │   │   │   └── react-refresh-runtime.min.js
│   │   │   ├── dom.js
│   │   │   ├── dom.min.js
│   │   │   ├── dom-ready.js
│   │   │   ├── dom-ready.min.js
│   │   │   ├── editor.js
│   │   │   ├── editor.min.js
│   │   │   ├── edit-post.js
│   │   │   ├── edit-post.min.js
│   │   │   ├── edit-site.js
│   │   │   ├── edit-site.min.js
│   │   │   ├── edit-widgets.js
│   │   │   ├── edit-widgets.min.js
│   │   │   ├── element.js
│   │   │   ├── element.min.js
│   │   │   ├── escape-html.js
│   │   │   ├── escape-html.min.js
│   │   │   ├── format-library.js
│   │   │   ├── format-library.min.js
│   │   │   ├── hooks.js
│   │   │   ├── hooks.min.js
│   │   │   ├── html-entities.js
│   │   │   ├── html-entities.min.js
│   │   │   ├── i18n.js
│   │   │   ├── i18n.min.js
│   │   │   ├── is-shallow-equal.js
│   │   │   ├── is-shallow-equal.min.js
│   │   │   ├── keyboard-shortcuts.js
│   │   │   ├── keyboard-shortcuts.min.js
│   │   │   ├── keycodes.js
│   │   │   ├── keycodes.min.js
│   │   │   ├── list-reusable-blocks.js
│   │   │   ├── list-reusable-blocks.min.js
│   │   │   ├── media-utils.js
│   │   │   ├── media-utils.min.js
│   │   │   ├── notices.js
│   │   │   ├── notices.min.js
│   │   │   ├── nux.js
│   │   │   ├── nux.min.js
│   │   │   ├── plugins.js
│   │   │   ├── plugins.min.js
│   │   │   ├── preferences.js
│   │   │   ├── preferences.min.js
│   │   │   ├── preferences-persistence.js
│   │   │   ├── preferences-persistence.min.js
│   │   │   ├── primitives.js
│   │   │   ├── primitives.min.js
│   │   │   ├── priority-queue.js
│   │   │   ├── priority-queue.min.js
│   │   │   ├── redux-routine.js
│   │   │   ├── redux-routine.min.js
│   │   │   ├── reusable-blocks.js
│   │   │   ├── reusable-blocks.min.js
│   │   │   ├── rich-text.js
│   │   │   ├── rich-text.min.js
│   │   │   ├── server-side-render.js
│   │   │   ├── server-side-render.min.js
│   │   │   ├── shortcode.js
│   │   │   ├── shortcode.min.js
│   │   │   ├── style-engine.js
│   │   │   ├── style-engine.min.js
│   │   │   ├── token-list.js
│   │   │   ├── token-list.min.js
│   │   │   ├── url.js
│   │   │   ├── url.min.js
│   │   │   ├── vendor
│   │   │   │   ├── lodash.js
│   │   │   │   ├── lodash.min.js
│   │   │   │   ├── moment.js
│   │   │   │   ├── moment.min.js
│   │   │   │   ├── react-dom.js
│   │   │   │   ├── react-dom.min.js
│   │   │   │   ├── react.js
│   │   │   │   ├── react.min.js
│   │   │   │   ├── regenerator-runtime.js
│   │   │   │   ├── regenerator-runtime.min.js
│   │   │   │   ├── wp-polyfill-dom-rect.js
│   │   │   │   ├── wp-polyfill-dom-rect.min.js
│   │   │   │   ├── wp-polyfill-element-closest.js
│   │   │   │   ├── wp-polyfill-element-closest.min.js
│   │   │   │   ├── wp-polyfill-fetch.js
│   │   │   │   ├── wp-polyfill-fetch.min.js
│   │   │   │   ├── wp-polyfill-formdata.js
│   │   │   │   ├── wp-polyfill-formdata.min.js
│   │   │   │   ├── wp-polyfill.js
│   │   │   │   ├── wp-polyfill.min.js
│   │   │   │   ├── wp-polyfill-node-contains.js
│   │   │   │   ├── wp-polyfill-node-contains.min.js
│   │   │   │   ├── wp-polyfill-object-fit.js
│   │   │   │   ├── wp-polyfill-object-fit.min.js
│   │   │   │   ├── wp-polyfill-url.js
│   │   │   │   └── wp-polyfill-url.min.js
│   │   │   ├── viewport.js
│   │   │   ├── viewport.min.js
│   │   │   ├── warning.js
│   │   │   ├── warning.min.js
│   │   │   ├── widgets.js
│   │   │   ├── widgets.min.js
│   │   │   ├── wordcount.js
│   │   │   └── wordcount.min.js
│   │   ├── heartbeat.js
│   │   ├── heartbeat.min.js
│   │   ├── hoverIntent.js
│   │   ├── hoverintent-js.min.js
│   │   ├── hoverIntent.min.js
│   │   ├── imagesloaded.min.js
│   │   ├── imgareaselect
│   │   │   ├── border-anim-h.gif
│   │   │   ├── border-anim-v.gif
│   │   │   ├── imgareaselect.css
│   │   │   ├── jquery.imgareaselect.js
│   │   │   └── jquery.imgareaselect.min.js
│   │   ├── jcrop
│   │   │   ├── Jcrop.gif
│   │   │   ├── jquery.Jcrop.min.css
│   │   │   └── jquery.Jcrop.min.js
│   │   ├── jquery
│   │   │   ├── jquery.color.min.js
│   │   │   ├── jquery.form.js
│   │   │   ├── jquery.form.min.js
│   │   │   ├── jquery.hotkeys.js
│   │   │   ├── jquery.hotkeys.min.js
│   │   │   ├── jquery.js
│   │   │   ├── jquery.masonry.min.js
│   │   │   ├── jquery-migrate.js
│   │   │   ├── jquery-migrate.min.js
│   │   │   ├── jquery.min.js
│   │   │   ├── jquery.query.js
│   │   │   ├── jquery.schedule.js
│   │   │   ├── jquery.serialize-object.js
│   │   │   ├── jquery.table-hotkeys.js
│   │   │   ├── jquery.table-hotkeys.min.js
│   │   │   ├── jquery.ui.touch-punch.js
│   │   │   ├── suggest.js
│   │   │   ├── suggest.min.js
│   │   │   └── ui
│   │   │       ├── accordion.js
│   │   │       ├── accordion.min.js
│   │   │       ├── autocomplete.js
│   │   │       ├── autocomplete.min.js
│   │   │       ├── button.js
│   │   │       ├── button.min.js
│   │   │       ├── checkboxradio.js
│   │   │       ├── checkboxradio.min.js
│   │   │       ├── controlgroup.js
│   │   │       ├── controlgroup.min.js
│   │   │       ├── core.js
│   │   │       ├── core.min.js
│   │   │       ├── datepicker.js
│   │   │       ├── datepicker.min.js
│   │   │       ├── dialog.js
│   │   │       ├── dialog.min.js
│   │   │       ├── draggable.js
│   │   │       ├── draggable.min.js
│   │   │       ├── droppable.js
│   │   │       ├── droppable.min.js
│   │   │       ├── effect-blind.js
│   │   │       ├── effect-blind.min.js
│   │   │       ├── effect-bounce.js
│   │   │       ├── effect-bounce.min.js
│   │   │       ├── effect-clip.js
│   │   │       ├── effect-clip.min.js
│   │   │       ├── effect-drop.js
│   │   │       ├── effect-drop.min.js
│   │   │       ├── effect-explode.js
│   │   │       ├── effect-explode.min.js
│   │   │       ├── effect-fade.js
│   │   │       ├── effect-fade.min.js
│   │   │       ├── effect-fold.js
│   │   │       ├── effect-fold.min.js
│   │   │       ├── effect-highlight.js
│   │   │       ├── effect-highlight.min.js
│   │   │       ├── effect.js
│   │   │       ├── effect.min.js
│   │   │       ├── effect-puff.js
│   │   │       ├── effect-puff.min.js
│   │   │       ├── effect-pulsate.js
│   │   │       ├── effect-pulsate.min.js
│   │   │       ├── effect-scale.js
│   │   │       ├── effect-scale.min.js
│   │   │       ├── effect-shake.js
│   │   │       ├── effect-shake.min.js
│   │   │       ├── effect-size.js
│   │   │       ├── effect-size.min.js
│   │   │       ├── effect-slide.js
│   │   │       ├── effect-slide.min.js
│   │   │       ├── effect-transfer.js
│   │   │       ├── effect-transfer.min.js
│   │   │       ├── menu.js
│   │   │       ├── menu.min.js
│   │   │       ├── mouse.js
│   │   │       ├── mouse.min.js
│   │   │       ├── progressbar.js
│   │   │       ├── progressbar.min.js
│   │   │       ├── resizable.js
│   │   │       ├── resizable.min.js
│   │   │       ├── selectable.js
│   │   │       ├── selectable.min.js
│   │   │       ├── selectmenu.js
│   │   │       ├── selectmenu.min.js
│   │   │       ├── slider.js
│   │   │       ├── slider.min.js
│   │   │       ├── sortable.js
│   │   │       ├── sortable.min.js
│   │   │       ├── spinner.js
│   │   │       ├── spinner.min.js
│   │   │       ├── tabs.js
│   │   │       ├── tabs.min.js
│   │   │       ├── tooltip.js
│   │   │       └── tooltip.min.js
│   │   ├── json2.js
│   │   ├── json2.min.js
│   │   ├── masonry.min.js
│   │   ├── mce-view.js
│   │   ├── mce-view.min.js
│   │   ├── media-audiovideo.js
│   │   ├── media-audiovideo.min.js
│   │   ├── media-editor.js
│   │   ├── media-editor.min.js
│   │   ├── mediaelement
│   │   │   ├── mediaelement-and-player.js
│   │   │   ├── mediaelement-and-player.min.js
│   │   │   ├── mediaelement.js
│   │   │   ├── mediaelement-migrate.js
│   │   │   ├── mediaelement-migrate.min.js
│   │   │   ├── mediaelement.min.js
│   │   │   ├── mediaelementplayer.css
│   │   │   ├── mediaelementplayer-legacy.css
│   │   │   ├── mediaelementplayer-legacy.min.css
│   │   │   ├── mediaelementplayer.min.css
│   │   │   ├── mejs-controls.png
│   │   │   ├── mejs-controls.svg
│   │   │   ├── renderers
│   │   │   │   ├── vimeo.js
│   │   │   │   └── vimeo.min.js
│   │   │   ├── wp-mediaelement.css
│   │   │   ├── wp-mediaelement.js
│   │   │   ├── wp-mediaelement.min.css
│   │   │   ├── wp-mediaelement.min.js
│   │   │   ├── wp-playlist.js
│   │   │   └── wp-playlist.min.js
│   │   ├── media-grid.js
│   │   ├── media-grid.min.js
│   │   ├── media-models.js
│   │   ├── media-models.min.js
│   │   ├── media-views.js
│   │   ├── media-views.min.js
│   │   ├── plupload
│   │   │   ├── handlers.js
│   │   │   ├── handlers.min.js
│   │   │   ├── license.txt
│   │   │   ├── moxie.js
│   │   │   ├── moxie.min.js
│   │   │   ├── plupload.js
│   │   │   ├── plupload.min.js
│   │   │   ├── wp-plupload.js
│   │   │   └── wp-plupload.min.js
│   │   ├── quicktags.js
│   │   ├── quicktags.min.js
│   │   ├── shortcode.js
│   │   ├── shortcode.min.js
│   │   ├── swfobject.js
│   │   ├── swfupload
│   │   │   ├── handlers.js
│   │   │   ├── handlers.min.js
│   │   │   ├── license.txt
│   │   │   └── swfupload.js
│   │   ├── thickbox
│   │   │   ├── loadingAnimation.gif
│   │   │   ├── macFFBgHack.png
│   │   │   ├── thickbox.css
│   │   │   └── thickbox.js
│   │   ├── tinymce
│   │   │   ├── langs
│   │   │   │   └── wp-langs-en.js
│   │   │   ├── license.txt
│   │   │   ├── plugins
│   │   │   │   ├── charmap
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── colorpicker
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── compat3x
│   │   │   │   │   ├── css
│   │   │   │   │   │   └── dialog.css
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── directionality
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── fullscreen
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── hr
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── image
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── link
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── lists
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── media
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── paste
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── tabfocus
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── textcolor
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── wordpress
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── wpautoresize
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── wpdialogs
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── wpeditimage
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── wpemoji
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── wpgallery
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── wplink
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   ├── wptextpattern
│   │   │   │   │   ├── plugin.js
│   │   │   │   │   └── plugin.min.js
│   │   │   │   └── wpview
│   │   │   │       ├── plugin.js
│   │   │   │       └── plugin.min.js
│   │   │   ├── skins
│   │   │   │   ├── lightgray
│   │   │   │   │   ├── content.inline.min.css
│   │   │   │   │   ├── content.min.css
│   │   │   │   │   ├── fonts
│   │   │   │   │   │   ├── tinymce.eot
│   │   │   │   │   │   ├── tinymce-small.eot
│   │   │   │   │   │   ├── tinymce-small.svg
│   │   │   │   │   │   ├── tinymce-small.ttf
│   │   │   │   │   │   ├── tinymce-small.woff
│   │   │   │   │   │   ├── tinymce.svg
│   │   │   │   │   │   ├── tinymce.ttf
│   │   │   │   │   │   └── tinymce.woff
│   │   │   │   │   ├── img
│   │   │   │   │   │   ├── anchor.gif
│   │   │   │   │   │   ├── loader.gif
│   │   │   │   │   │   ├── object.gif
│   │   │   │   │   │   └── trans.gif
│   │   │   │   │   └── skin.min.css
│   │   │   │   └── wordpress
│   │   │   │       ├── images
│   │   │   │       │   ├── audio.png
│   │   │   │       │   ├── dashicon-edit.png
│   │   │   │       │   ├── dashicon-no.png
│   │   │   │       │   ├── embedded.png
│   │   │   │       │   ├── gallery-2x.png
│   │   │   │       │   ├── gallery.png
│   │   │   │       │   ├── more-2x.png
│   │   │   │       │   ├── more.png
│   │   │   │       │   ├── pagebreak-2x.png
│   │   │   │       │   ├── pagebreak.png
│   │   │   │       │   ├── playlist-audio.png
│   │   │   │       │   ├── playlist-video.png
│   │   │   │       │   └── video.png
│   │   │   │       └── wp-content.css
│   │   │   ├── themes
│   │   │   │   ├── inlite
│   │   │   │   │   ├── theme.js
│   │   │   │   │   └── theme.min.js
│   │   │   │   └── modern
│   │   │   │       ├── theme.js
│   │   │   │       └── theme.min.js
│   │   │   ├── tinymce.min.js
│   │   │   ├── tiny_mce_popup.js
│   │   │   ├── utils
│   │   │   │   ├── editable_selects.js
│   │   │   │   ├── form_utils.js
│   │   │   │   ├── mctabs.js
│   │   │   │   └── validate.js
│   │   │   ├── wp-tinymce.js
│   │   │   └── wp-tinymce.php
│   │   ├── twemoji.js
│   │   ├── twemoji.min.js
│   │   ├── tw-sack.js
│   │   ├── tw-sack.min.js
│   │   ├── underscore.js
│   │   ├── underscore.min.js
│   │   ├── utils.js
│   │   ├── utils.min.js
│   │   ├── wp-ajax-response.js
│   │   ├── wp-ajax-response.min.js
│   │   ├── wp-api.js
│   │   ├── wp-api.min.js
│   │   ├── wp-auth-check.js
│   │   ├── wp-auth-check.min.js
│   │   ├── wp-backbone.js
│   │   ├── wp-backbone.min.js
│   │   ├── wp-custom-header.js
│   │   ├── wp-custom-header.min.js
│   │   ├── wpdialog.js
│   │   ├── wpdialog.min.js
│   │   ├── wp-embed.js
│   │   ├── wp-embed.min.js
│   │   ├── wp-embed-template.js
│   │   ├── wp-embed-template.min.js
│   │   ├── wp-emoji.js
│   │   ├── wp-emoji-loader.js
│   │   ├── wp-emoji-loader.min.js
│   │   ├── wp-emoji.min.js
│   │   ├── wp-emoji-release.min.js
│   │   ├── wplink.js
│   │   ├── wplink.min.js
│   │   ├── wp-list-revisions.js
│   │   ├── wp-list-revisions.min.js
│   │   ├── wp-lists.js
│   │   ├── wp-lists.min.js
│   │   ├── wp-pointer.js
│   │   ├── wp-pointer.min.js
│   │   ├── wp-sanitize.js
│   │   ├── wp-sanitize.min.js
│   │   ├── wp-util.js
│   │   ├── wp-util.min.js
│   │   ├── zxcvbn-async.js
│   │   ├── zxcvbn-async.min.js
│   │   └── zxcvbn.min.js
│   ├── kses.php
│   ├── l10n.php
│   ├── link-template.php
│   ├── load.php
│   ├── locale.php
│   ├── media.php
│   ├── media-template.php
│   ├── meta.php
│   ├── ms-blogs.php
│   ├── ms-default-constants.php
│   ├── ms-default-filters.php
│   ├── ms-deprecated.php
│   ├── ms-files.php
│   ├── ms-functions.php
│   ├── ms-load.php
│   ├── ms-network.php
│   ├── ms-settings.php
│   ├── ms-site.php
│   ├── nav-menu.php
│   ├── nav-menu-template.php
│   ├── option.php
│   ├── php-compat
│   │   └── readonly.php
│   ├── PHPMailer
│   │   ├── Exception.php
│   │   ├── PHPMailer.php
│   │   └── SMTP.php
│   ├── pluggable-deprecated.php
│   ├── pluggable.php
│   ├── plugin.php
│   ├── pomo
│   │   ├── entry.php
│   │   ├── mo.php
│   │   ├── plural-forms.php
│   │   ├── po.php
│   │   ├── streams.php
│   │   └── translations.php
│   ├── post-formats.php
│   ├── post.php
│   ├── post-template.php
│   ├── post-thumbnail-template.php
│   ├── query.php
│   ├── random_compat
│   │   ├── byte_safe_strings.php
│   │   ├── cast_to_int.php
│   │   ├── error_polyfill.php
│   │   ├── random_bytes_com_dotnet.php
│   │   ├── random_bytes_dev_urandom.php
│   │   ├── random_bytes_libsodium_legacy.php
│   │   ├── random_bytes_libsodium.php
│   │   ├── random_bytes_mcrypt.php
│   │   ├── random_int.php
│   │   └── random.php
│   ├── registration-functions.php
│   ├── registration.php
│   ├── Requests
│   │   ├── Auth
│   │   │   └── Basic.php
│   │   ├── Auth.php
│   │   ├── Cookie
│   │   │   └── Jar.php
│   │   ├── Cookie.php
│   │   ├── Exception
│   │   │   ├── HTTP
│   │   │   │   ├── 304.php
│   │   │   │   ├── 305.php
│   │   │   │   ├── 306.php
│   │   │   │   ├── 400.php
│   │   │   │   ├── 401.php
│   │   │   │   ├── 402.php
│   │   │   │   ├── 403.php
│   │   │   │   ├── 404.php
│   │   │   │   ├── 405.php
│   │   │   │   ├── 406.php
│   │   │   │   ├── 407.php
│   │   │   │   ├── 408.php
│   │   │   │   ├── 409.php
│   │   │   │   ├── 410.php
│   │   │   │   ├── 411.php
│   │   │   │   ├── 412.php
│   │   │   │   ├── 413.php
│   │   │   │   ├── 414.php
│   │   │   │   ├── 415.php
│   │   │   │   ├── 416.php
│   │   │   │   ├── 417.php
│   │   │   │   ├── 418.php
│   │   │   │   ├── 428.php
│   │   │   │   ├── 429.php
│   │   │   │   ├── 431.php
│   │   │   │   ├── 500.php
│   │   │   │   ├── 501.php
│   │   │   │   ├── 502.php
│   │   │   │   ├── 503.php
│   │   │   │   ├── 504.php
│   │   │   │   ├── 505.php
│   │   │   │   ├── 511.php
│   │   │   │   └── Unknown.php
│   │   │   ├── HTTP.php
│   │   │   ├── Transport
│   │   │   │   └── cURL.php
│   │   │   └── Transport.php
│   │   ├── Exception.php
│   │   ├── Hooker.php
│   │   ├── Hooks.php
│   │   ├── IDNAEncoder.php
│   │   ├── IPv6.php
│   │   ├── IRI.php
│   │   ├── Proxy
│   │   │   └── HTTP.php
│   │   ├── Proxy.php
│   │   ├── Response
│   │   │   └── Headers.php
│   │   ├── Response.php
│   │   ├── Session.php
│   │   ├── SSL.php
│   │   ├── Transport
│   │   │   ├── cURL.php
│   │   │   └── fsockopen.php
│   │   ├── Transport.php
│   │   └── Utility
│   │       ├── CaseInsensitiveDictionary.php
│   │       └── FilteredIterator.php
│   ├── rest-api
│   │   ├── class-wp-rest-request.php
│   │   ├── class-wp-rest-response.php
│   │   ├── class-wp-rest-server.php
│   │   ├── endpoints
│   │   │   ├── class-wp-rest-application-passwords-controller.php
│   │   │   ├── class-wp-rest-attachments-controller.php
│   │   │   ├── class-wp-rest-autosaves-controller.php
│   │   │   ├── class-wp-rest-block-directory-controller.php
│   │   │   ├── class-wp-rest-block-pattern-categories-controller.php
│   │   │   ├── class-wp-rest-block-patterns-controller.php
│   │   │   ├── class-wp-rest-block-renderer-controller.php
│   │   │   ├── class-wp-rest-blocks-controller.php
│   │   │   ├── class-wp-rest-block-types-controller.php
│   │   │   ├── class-wp-rest-comments-controller.php
│   │   │   ├── class-wp-rest-controller.php
│   │   │   ├── class-wp-rest-edit-site-export-controller.php
│   │   │   ├── class-wp-rest-global-styles-controller.php
│   │   │   ├── class-wp-rest-menu-items-controller.php
│   │   │   ├── class-wp-rest-menu-locations-controller.php
│   │   │   ├── class-wp-rest-menus-controller.php
│   │   │   ├── class-wp-rest-pattern-directory-controller.php
│   │   │   ├── class-wp-rest-plugins-controller.php
│   │   │   ├── class-wp-rest-posts-controller.php
│   │   │   ├── class-wp-rest-post-statuses-controller.php
│   │   │   ├── class-wp-rest-post-types-controller.php
│   │   │   ├── class-wp-rest-revisions-controller.php
│   │   │   ├── class-wp-rest-search-controller.php
│   │   │   ├── class-wp-rest-settings-controller.php
│   │   │   ├── class-wp-rest-sidebars-controller.php
│   │   │   ├── class-wp-rest-site-health-controller.php
│   │   │   ├── class-wp-rest-taxonomies-controller.php
│   │   │   ├── class-wp-rest-templates-controller.php
│   │   │   ├── class-wp-rest-terms-controller.php
│   │   │   ├── class-wp-rest-themes-controller.php
│   │   │   ├── class-wp-rest-url-details-controller.php
│   │   │   ├── class-wp-rest-users-controller.php
│   │   │   ├── class-wp-rest-widgets-controller.php
│   │   │   └── class-wp-rest-widget-types-controller.php
│   │   ├── fields
│   │   │   ├── class-wp-rest-comment-meta-fields.php
│   │   │   ├── class-wp-rest-meta-fields.php
│   │   │   ├── class-wp-rest-post-meta-fields.php
│   │   │   ├── class-wp-rest-term-meta-fields.php
│   │   │   └── class-wp-rest-user-meta-fields.php
│   │   └── search
│   │       ├── class-wp-rest-post-format-search-handler.php
│   │       ├── class-wp-rest-post-search-handler.php
│   │       ├── class-wp-rest-search-handler.php
│   │       └── class-wp-rest-term-search-handler.php
│   ├── rest-api.php
│   ├── revision.php
│   ├── rewrite.php
│   ├── robots-template.php
│   ├── rss-functions.php
│   ├── rss.php
│   ├── script-loader.php
│   ├── session.php
│   ├── shortcodes.php
│   ├── SimplePie
│   │   ├── Author.php
│   │   ├── Cache
│   │   │   ├── Base.php
│   │   │   ├── DB.php
│   │   │   ├── File.php
│   │   │   ├── Memcached.php
│   │   │   ├── Memcache.php
│   │   │   ├── MySQL.php
│   │   │   └── Redis.php
│   │   ├── Cache.php
│   │   ├── Caption.php
│   │   ├── Category.php
│   │   ├── Content
│   │   │   └── Type
│   │   │       └── Sniffer.php
│   │   ├── Copyright.php
│   │   ├── Core.php
│   │   ├── Credit.php
│   │   ├── Decode
│   │   │   └── HTML
│   │   │       └── Entities.php
│   │   ├── Enclosure.php
│   │   ├── Exception.php
│   │   ├── File.php
│   │   ├── gzdecode.php
│   │   ├── HTTP
│   │   │   └── Parser.php
│   │   ├── IRI.php
│   │   ├── Item.php
│   │   ├── Locator.php
│   │   ├── Misc.php
│   │   ├── Net
│   │   │   └── IPv6.php
│   │   ├── Parse
│   │   │   └── Date.php
│   │   ├── Parser.php
│   │   ├── Rating.php
│   │   ├── Registry.php
│   │   ├── Restriction.php
│   │   ├── Sanitize.php
│   │   ├── Source.php
│   │   └── XML
│   │       └── Declaration
│   │           └── Parser.php
│   ├── sitemaps
│   │   ├── class-wp-sitemaps-index.php
│   │   ├── class-wp-sitemaps.php
│   │   ├── class-wp-sitemaps-provider.php
│   │   ├── class-wp-sitemaps-registry.php
│   │   ├── class-wp-sitemaps-renderer.php
│   │   ├── class-wp-sitemaps-stylesheet.php
│   │   └── providers
│   │       ├── class-wp-sitemaps-posts.php
│   │       ├── class-wp-sitemaps-taxonomies.php
│   │       └── class-wp-sitemaps-users.php
│   ├── sitemaps.php
│   ├── sodium_compat
│   │   ├── autoload.php
│   │   ├── autoload-php7.php
│   │   ├── composer.json
│   │   ├── lib
│   │   │   ├── constants.php
│   │   │   ├── namespaced.php
│   │   │   ├── php72compat_const.php
│   │   │   ├── php72compat.php
│   │   │   ├── ristretto255.php
│   │   │   ├── sodium_compat.php
│   │   │   └── stream-xchacha20.php
│   │   ├── LICENSE
│   │   ├── namespaced
│   │   │   ├── Compat.php
│   │   │   ├── Core
│   │   │   │   ├── BLAKE2b.php
│   │   │   │   ├── ChaCha20
│   │   │   │   │   ├── Ctx.php
│   │   │   │   │   └── IetfCtx.php
│   │   │   │   ├── ChaCha20.php
│   │   │   │   ├── Curve25519
│   │   │   │   │   ├── Fe.php
│   │   │   │   │   ├── Ge
│   │   │   │   │   │   ├── Cached.php
│   │   │   │   │   │   ├── P1p1.php
│   │   │   │   │   │   ├── P2.php
│   │   │   │   │   │   ├── P3.php
│   │   │   │   │   │   └── Precomp.php
│   │   │   │   │   └── H.php
│   │   │   │   ├── Curve25519.php
│   │   │   │   ├── Ed25519.php
│   │   │   │   ├── HChaCha20.php
│   │   │   │   ├── HSalsa20.php
│   │   │   │   ├── Poly1305
│   │   │   │   │   └── State.php
│   │   │   │   ├── Poly1305.php
│   │   │   │   ├── Salsa20.php
│   │   │   │   ├── SipHash.php
│   │   │   │   ├── Util.php
│   │   │   │   ├── X25519.php
│   │   │   │   ├── XChaCha20.php
│   │   │   │   └── Xsalsa20.php
│   │   │   ├── Crypto.php
│   │   │   └── File.php
│   │   └── src
│   │       ├── Compat.php
│   │       ├── Core
│   │       │   ├── Base64
│   │       │   │   ├── Common.php
│   │       │   │   ├── Original.php
│   │       │   │   └── UrlSafe.php
│   │       │   ├── BLAKE2b.php
│   │       │   ├── ChaCha20
│   │       │   │   ├── Ctx.php
│   │       │   │   └── IetfCtx.php
│   │       │   ├── ChaCha20.php
│   │       │   ├── Curve25519
│   │       │   │   ├── Fe.php
│   │       │   │   ├── Ge
│   │       │   │   │   ├── Cached.php
│   │       │   │   │   ├── P1p1.php
│   │       │   │   │   ├── P2.php
│   │       │   │   │   ├── P3.php
│   │       │   │   │   └── Precomp.php
│   │       │   │   ├── H.php
│   │       │   │   └── README.md
│   │       │   ├── Curve25519.php
│   │       │   ├── Ed25519.php
│   │       │   ├── HChaCha20.php
│   │       │   ├── HSalsa20.php
│   │       │   ├── Poly1305
│   │       │   │   └── State.php
│   │       │   ├── Poly1305.php
│   │       │   ├── Ristretto255.php
│   │       │   ├── Salsa20.php
│   │       │   ├── SecretStream
│   │       │   │   └── State.php
│   │       │   ├── SipHash.php
│   │       │   ├── Util.php
│   │       │   ├── X25519.php
│   │       │   ├── XChaCha20.php
│   │       │   └── XSalsa20.php
│   │       ├── Core32
│   │       │   ├── BLAKE2b.php
│   │       │   ├── ChaCha20
│   │       │   │   ├── Ctx.php
│   │       │   │   └── IetfCtx.php
│   │       │   ├── ChaCha20.php
│   │       │   ├── Curve25519
│   │       │   │   ├── Fe.php
│   │       │   │   ├── Ge
│   │       │   │   │   ├── Cached.php
│   │       │   │   │   ├── P1p1.php
│   │       │   │   │   ├── P2.php
│   │       │   │   │   ├── P3.php
│   │       │   │   │   └── Precomp.php
│   │       │   │   ├── H.php
│   │       │   │   └── README.md
│   │       │   ├── Curve25519.php
│   │       │   ├── Ed25519.php
│   │       │   ├── HChaCha20.php
│   │       │   ├── HSalsa20.php
│   │       │   ├── Int32.php
│   │       │   ├── Int64.php
│   │       │   ├── Poly1305
│   │       │   │   └── State.php
│   │       │   ├── Poly1305.php
│   │       │   ├── Salsa20.php
│   │       │   ├── SecretStream
│   │       │   │   └── State.php
│   │       │   ├── SipHash.php
│   │       │   ├── Util.php
│   │       │   ├── X25519.php
│   │       │   ├── XChaCha20.php
│   │       │   └── XSalsa20.php
│   │       ├── Crypto32.php
│   │       ├── Crypto.php
│   │       ├── File.php
│   │       ├── PHP52
│   │       │   └── SplFixedArray.php
│   │       └── SodiumException.php
│   ├── spl-autoload-compat.php
│   ├── style-engine
│   │   ├── class-wp-style-engine-css-declarations.php
│   │   ├── class-wp-style-engine-css-rule.php
│   │   ├── class-wp-style-engine-css-rules-store.php
│   │   ├── class-wp-style-engine.php
│   │   └── class-wp-style-engine-processor.php
│   ├── style-engine.php
│   ├── taxonomy.php
│   ├── template-canvas.php
│   ├── template-loader.php
│   ├── template.php
│   ├── Text
│   │   ├── Diff
│   │   │   ├── Engine
│   │   │   │   ├── native.php
│   │   │   │   ├── shell.php
│   │   │   │   ├── string.php
│   │   │   │   └── xdiff.php
│   │   │   ├── Renderer
│   │   │   │   └── inline.php
│   │   │   └── Renderer.php
│   │   └── Diff.php
│   ├── theme-compat
│   │   ├── comments.php
│   │   ├── embed-404.php
│   │   ├── embed-content.php
│   │   ├── embed.php
│   │   ├── footer-embed.php
│   │   ├── footer.php
│   │   ├── header-embed.php
│   │   ├── header.php
│   │   └── sidebar.php
│   ├── theme-i18n.json
│   ├── theme.json
│   ├── theme.php
│   ├── theme-templates.php
│   ├── update.php
│   ├── user.php
│   ├── vars.php
│   ├── version.php
│   ├── widgets
│   │   ├── class-wp-nav-menu-widget.php
│   │   ├── class-wp-widget-archives.php
│   │   ├── class-wp-widget-block.php
│   │   ├── class-wp-widget-calendar.php
│   │   ├── class-wp-widget-categories.php
│   │   ├── class-wp-widget-custom-html.php
│   │   ├── class-wp-widget-links.php
│   │   ├── class-wp-widget-media-audio.php
│   │   ├── class-wp-widget-media-gallery.php
│   │   ├── class-wp-widget-media-image.php
│   │   ├── class-wp-widget-media.php
│   │   ├── class-wp-widget-media-video.php
│   │   ├── class-wp-widget-meta.php
│   │   ├── class-wp-widget-pages.php
│   │   ├── class-wp-widget-recent-comments.php
│   │   ├── class-wp-widget-recent-posts.php
│   │   ├── class-wp-widget-rss.php
│   │   ├── class-wp-widget-search.php
│   │   ├── class-wp-widget-tag-cloud.php
│   │   └── class-wp-widget-text.php
│   ├── widgets.php
│   ├── wlwmanifest.xml
│   ├── wp-db.php
│   └── wp-diff.php
├── wp-links-opml.php
├── wp-load.php
├── wp-login.php
├── wp-mail.php
├── wp-settings.php
├── wp-signup.php
├── wp-trackback.php
└── xmlrpc.php

345 directories, 2960 files
```

เกือบ 3,000 ไฟล์ เยอะกว่าเงินในบัญชีฉันอีก จะให้ไปนั่ง cat ดูทีละไฟล์ก็เสียเวลาเกินไป

Step 4 ไดเรกทอรี wp-content

คำสั่ง cd ใช้สำหรับเปลี่ยนไดเรกทอรีหรือโฟลเดอร์ปัจจุบันในเทอร์มินัล

```
cd wp-content
```

จะได้

```
┌──(kali㉿kali)-[~/Downloads/Fake_News/html/wp-content]
└─$ ls
cache  index.php  plugins  themes  upgrade  uploads
```

index.php เป็นไฟล์ ที่เหลือเป็นไดเรกทอรี 

ฉันเลือกที่จะ cd plugins เพราะดูน่าสงสัยสุด สงสัยว่าจะซ่อนอะไรไว้

```
┌──(kali㉿kali)-[~/Downloads/Fake_News/html/wp-content]
└─$ cd plugins   
                                                                                                                                      
┌──(kali㉿kali)-[~/…/Fake_News/html/wp-content/plugins]
└─$ ls
akismet  hello.php  index.php  plugin-manager
```
akismet และ plugin-manager เป็นไดเรกทอรี ที่เหลือเป็นไฟล์


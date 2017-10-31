---
sidebar: home_sidebar
title: Aplikasi Google
permalink: gapps.html
---
Aplikasi Google adalah aplikasi ber-hak-milik dari Google yang telah terpasang sebelumnya di sebagian besar perangkat Android, seperti Play Store, Gmail, Maps, dll.

Karena pembatasan lisensi inilah aplikasi ini tidak dapat digabunh sebagai aplikasi pra-instal pada LineageOS dan harus diinstal secara terpisah.

Aplikasi Google tidak diperlukan untuk menyalakan atau menjalankan LineageOS, namun banyak pengguna merasa bahwa banyak keuntungan/manfaat dari ekosistem Android jika menpunyai aplikasi ini. 

Aplikasi ini sudah di packing oleh pengembang yang terpisah dari tim LineageOS, dan tautan unduhan telah disediakan untuk mempermudah Kamu saja. 

Meskipun ada pilihan untuk melakukan "pencadangan" aplikasi Google di perangkat Kamu dan kemudian "memulihkan"-nya, namun hal ini memerlukan langkah tambahan yang tidak bisa tercakup di sini.

Proyek Open GApps dan paket Google apps lainnya  **tidak didukung** penggunaannya oleh LineageOS dalam bentuk apapun.

## Unduhan

Setiap paket tergantung pada arsitektur dan versi OS yang Kami pakai, yang bisa kamu lihat secara detil ([Daftar Gawai](devices.html)).

|Versi OS                  |Link                                                   |
|--------------------------|-------------------------------------------------------|
|Lineage 14.1 (Android 7.1)|[OpenGApps](http://opengapps.org/?api=7.1&variant=nano)|
|Lineage 13.0 (Android 6.0)|[OpenGApps](http://opengapps.org/?api=6.0&variant=nano)|

## Installation

Google apps should be installed via recovery **immediately** after installing LineageOS. Exact steps vary, but the process is similar to that of installing LineageOS:

{% include important.html content="If you reboot into LineageOS before installing Google apps, you must factory reset and then install them, otherwise expect crashes." %}

1. Copy the Google apps zipfile to `/sdcard/`
    * Using [adb](adb_fastboot_guide.html): `adb push filename.zip /sdcard/`
2. After installing LineageOS, choose "install zip" or "Apply update" in recovery, and navigate to the zipfile loaded earlier.
3. Reboot to system (i.e. LineageOS).

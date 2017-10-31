---
sidebar: home_sidebar
title: Google apps
permalink: gapps.html
---
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

|Versi OS                  |Link                                                   |
|--------------------------|-------------------------------------------------------|
|Lineage 14.1 (Android 7.1)|[OpenGApps](http://opengapps.org/?api=7.1&variant=nano)|
|Lineage 13.0 (Android 6.0)|[OpenGApps](http://opengapps.org/?api=6.0&variant=nano)|

Google apps harus dipasang lewat recovery **langsung** setelah pemasangan LineageOS sebelum boot pertama. Langkah pemasangan bisa bervariasi, tetapi umumnya langkahnya hampir sama dengan langkah pemasangan LineageOS:

{% include important.html content="Jika kamu me-reboot setelah memasang LineageOS sebelum memasang Google apps, kamu harus factory reset dulu baru memasangnya, jika tidak bisa terjadi masalah." %}

1. Salin file zip Google apps ke `/sdcard/`
    * Menggunakan [adb](adb_fastboot_guide.html): `adb push namafile.zip /sdcard/`
2. Setelah memasang LineageOS, pilih "install zip" atau "Apply update" dalam recovery, dan arahkan ke lokasi file zip sebelumnya.
3. Reboot ke OS (i.e. LineageOS).

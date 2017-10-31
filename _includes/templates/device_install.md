{% assign device = site.data.devices[page.device] %}
## Peryaratan umum

{% include important.html content="Bacalah instruksi berikutu secara keseluruhan setidaknya sekali sebelum mempraktekkannya langsung untuk mencegah masalah gara-gara ada langkah yang terlewatkan!" %}

1. Pastikn komputer kamu sudah terpasang `adb`{% unless device.install_method != 'heimdall' or device.install_method != 'dd' %} and `fastboot`{% endunless %} yang berfungsi normal. Instruksi pengaturan bisa kamu temukan di [sini]({{ "adb_fastboot_guide.html" | relative_url }}).
2. Aktifkan [USB debugging]({{ "adb_fastboot_guide.html#setting-up-adb" | relative_url }}) pada gawai kamu.

{% if device.required_bootloader %}
## Persyratan khusus

{% capture bootloader %}
Gawai kamu harus dalam versi bootloader {% for el in device.required_bootloader %} {% if forloop.last %} `{{ el }}` {% else %} `{{ el }}` / {% endif %} {% endfor %}, jika tidak, panduan dalam halaman ini tidak bisa kamu pakai.
Versi bootloader bisa kamu periksa menggunakn perinth `getprop ro.bootloader` dalam aplikasi terminal atau `adb shell` dari jendela command prompt (Windows) atau terminal (Linux atau macOS).
{% endcapture %}
{% include warning.html content=bootloader %}
{% endif %}

{% if device.install_method %}
{% capture recovery_install_method %}templates/recovery_install_{{ device.install_method }}.md{% endcapture %}
{% include {{ recovery_install_method }} %}
{% else %}
## Membuka kunci bootloader / Memasang custom recovery

Tidak ada panduan memasang recovery untuk gawai discontinued ini.
{% endif %}

## Memasang LineageOS dari recovery

{% if device.maintainers %}
1. Unduh [paket ROM LineageOS](https://download.lineageos.org/{{ device.codename }}) yang kamu ingin pasang atau [buat]({{ "devices/" | append: device.codename | append: "/build" | relative_url }}) sendiri paket ROM kamu.
{% else %}
1. [Buat]({{ "devices/" | append: device.codename | append: "/build" | relative_url }}) sendiri paket ROM LineageOS.
{% endif %}
    * Silahkan unduh paket aplikasi pihak ke-3 semisal [Google Apps]({{ "gapps.html" | relative_url }})
2. Letakkan rom LineageOS `.zip`, bersama dengan paket .zip lain ke `/sdcard` di luar folder:
    * Dengan adb: `adb push filename.zip /sdcard/`
    * Kamu bisa menggunakan cara yang paling mudah untuk kamu. `adb` sendiri bisa dipakai pada semua jenis gawai, dan berfungsi dengan baik pada Android maupun recovery mode, yang mempunyai
        USB debugging aktif.
3. Jika gawai kamu belum dalam mode recovery, reboot dulu ke recovery:
    * {{ device.recovery_boot }}
4. _(Opsional, tapi disarankan)_: Pilih tombol **Backup** untuk membuat cadangan.
5. Pilih **Wipe** kemudian **Advanced Wipe**.
6. Pilih partisi *Cache*, *System* dan *Data* untuk di bersihkan kemudian **Swipe to Wipe**.
7. Go back untuk kembali ke menu utama, kemudian pilih **Install**.
8. Arahkan ke `/sdcard`, dan pilih paket rom LineageOS `.zip`.
9. Ikuti saja panduan yang muncul pada layar untuk memasang paket zip.
10. _(Optional)_: Pasang paket tambahan lain dengan cara yang sama.
    {% include note.html content="Jika kamu ingin memasang Google Apps pada gawai kamu, ikuti langkah berikut **sebelum** reboot pertama!" %}
11. _(Optional)_: Root gawai kamu dengan memasang [LineageOS su add-on](https://download.lineageos.org/extras){% if device.architecture %} (use the `{{ device.architecture }}` package){% endif %} atau dengan [cara lain](https://www.google.com/amp/www.knoacc.org/2017/04/penjelasan-magisk-root-cara-sembunyikan-status-root.html) yang kamu sukai.
12. Setelah proses pemasangan sudah selesai, kembali ke menu utama, pilih **Reboot**, dan pilih **System**.

## Mendapatkan bantuan

Jika kamu ada pertanyaan atau mentok pada salah satu langkah di tas, silahkan bertanya pada [subreddit kami](https://reddit.com/r/LineageOS) atau di [#LineageOS on freenode](https://webchat.freenode.net/?channels=LineageOS).
 sure your computer has working `adb`{% unless device.install_method != 'heimdall' or device.install_method != 'dd' %} and `fastb ).

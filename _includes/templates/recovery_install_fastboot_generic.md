{% if site.data.devices[page.device].custom_twrp_codename %}
{% assign twrp_codename = site.data.devices[page.device].custom_twrp_codename %}
{% else %}
{% assign twrp_codename = site.data.devices[page.device].codename %}
{% endif %}

## Memasang custom recovery dengan `fastboot`

{% if site.data.devices[page.device].custom_twrp_link %}
1. Unduh custom recovery - kamu bisa mengunduh [TWRP]({{ site.data.devices[page.device].custom_twrp_link }}).
{% else %}
1. Unduh custom recovery - kamu bisa mengunduh dari [TWRP](https://dl.twrp.me/{{ twrp_codename }}). Unduh saja file recovery terbaru, dengan nama seperti `twrp-x.x.x-x-{{ twrp_codename }}.img`.
{% endif %}
2. Hubungkan gawai ke PC dengan kabel USB.
3. Pada komputer, buka jendela command prompt (pada Windows) atau terminal (pada Linux atau macOS), dan ketik:

        adb reboot bootloader

    {% if site.data.devices[page.device].download_boot %}
    Kamu juga bisa masuk ke mode fastboot dengan kombinasi tombol:

    * {{ site.data.devices[page.device].download_boot }}
    {% endif %}
4. Setelah gawai berada dalam fastboot mode, cek gawai kamu di PC dengan mengetik:

        fastboot devices

    {% include tip.html content="Jika kamu melihat `no permissions fastboot` saat memakai Linux atau macOS, cobalah menjalankan `fastboot` sebagai root." %}
5. Flash recovery ke gawai kamu:

        fastboot flash recovery twrp-x.x.x-x-{{ twrp_codename }}.img

    {% include tip.html content="Nama file mungkin tidak sama persis seperti dalam perintah ini, jadi sesuaikan saja." %}

6. Sekarang restart ke mode recovery untuk memeriksa pemasangan:
    * {{ site.data.devices[page.device].recovery_boot }}

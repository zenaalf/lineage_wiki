{% unless site.data.devices[page.device].no_oem_unlock_switch %}
## Membuka kunci bootloader (UBL)

{% include note.html content="Langkah berikut ini hanya perlu dilakukan sekali tiap gawai." %}
{% include warning.html content="Membuka kunci bootloader akan menghapus semua data di gawai kamu!
Sebelum memulai, pastikan data yang dianggap penting kamu cadangkan ke PC atau akun Google kamu atau media pencadangan lain." %}

1. Kunjungi [ website resmi unlock Xiaomi](http://en.miui.com/unlock/).
2. Ajukan ijin untuk membuka kunci bootloader.
3. Unduh Mi Unlock app (PC kamu harus memakai Windows).
4. Tunggu dengan sabar hingga kamu dapat persetujuan, yang bisa jadi hingga beberapa hari.
5. Setelah Kamu dapat ijin, jalankan Mi Unlock app dan ikuti petunjuk yang diberikan.
6. Setelah gawai dan akun Mi berhasil diverifikasi, kunci bootloader seharusnya sudah terbuka.
7. Karena gawai sudah di reset sepenuhnya, kamu perlu megaktifkan kembali pilihan USB debugging untuk melanjutkan.

{% include tip.html content="Akun Mi dibutuhkan untuk meminta ijin. Kamu tidak perlu meminta ijin ulang untuk membuka kunci gawai baru dengan akun yang sama. Tetapi ingat, satu akun hanya bisa boleh melakukan pembukaan kunci booloader (UBL) satu gawai baru tiap 30 hari." %}
{% include tip.html content="Sangat disarankan untuk memakai rom dev (beta) terbaru sebelum melakukan proses UBL." %}
{% endunless %}

{% include templates/recovery_install_fastboot_generic.md %}
{% if site.data.devices[page.device].no_oem_unlock_switch %}
{% include tip.html content="Sangat disarankan untuk memakai rom dev (beta) terbaru sebelum memasang custom recovery." %}
{% endif %}

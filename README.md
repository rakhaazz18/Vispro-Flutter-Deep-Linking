1. Perbedaan Route & Deep Link

Route (Flutter): Navigasi di dalam aplikasi (contoh: /home, /detail/123) hanya jalan kalau aplikasi sudah terbuka

Deep Link (Android): Tautan dari luar aplikasi (contoh: myapp://detail/123) bisa buka aplikasi dan langsung ke halaman tertentu

2. Kenapa Perlu Intent Filter

Android perlu tahu aplikasi mana yang menangani link tersebut

Intent filter menentukan skema, host, dan path link yang cocok untuk membuka aplikasi

Cara kerja uni_links

uni_links jadi jembatan antara link dari Android/IOS dan Flutter

Aplikasi berjalan (hot start)

Link dikirim sebagai URL dan bisa digunakan untuk pindah halaman

Saat Deep Link dibuka saat aplikasi sudah jalan

Aplikasi tidak restart

URL link masuk lewat listener uni_links

Developer harus menangani URL tersebut untuk navigasi manual ke halaman tujuan

Debugging

Masalah: Aplikasi terbuka lewat adb, tapi tidak pindah ke halaman detail

Cek:

File AndroidManifest.xml pastikan intent-filter sudah cocok contohnya : (scheme, host, path)

Kalau sudah cocok:

Cek kode listener uni_links make sure URL ditangani dan diarahkan ke halaman yang tepat


---------------------------------------------------------------------------------------------


                                        SUMMARY

Project ini bertujuan untuk memahami dan mengimplementasikan Deep Linking di Flutter agar aplikasi bisa membuka layar tertentu langsung dari tautan khusus,misalnya myapp://details/42.Prosesnya membuat project Flutter dengan beberapa routes,menambahkan intent filter di AndorindManifest.xml untuk bisa membaca custom URL,lalu menggunakan package uni_links untuk membaca dan memproses link tersebut baik saat aplikasi baru di run dan saat running.Lalu tambahkan command adb di terminal,user dapat mengetes link tadi apakah bisa berfungsi dan berpindah halaman sesuai dengan arahan Deep Linking apa tidak

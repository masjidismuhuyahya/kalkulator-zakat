🕌 Kalkulator Zakat Berbasis Web

Kalkulator Zakat adalah aplikasi berbasis web (Single Page Application) yang dirancang untuk memudahkan umat Islam dalam menghitung kewajiban zakat mereka secara akurat dan real-time. Aplikasi ini dibangun dengan berlandaskan pada kaidah Fikih Zakat klasik dan disesuaikan dengan standar yang berlaku (seperti nisab emas, perak, dan hasil panen).

Aplikasi ini berjalan sepenuhnya di sisi klien (browser) tanpa memerlukan server backend atau database.

✨ Fitur Utama

Aplikasi ini mencakup 5 jenis perhitungan zakat utama:

Zakat Fitrah

Menghitung zakat fitrah berdasarkan jumlah tanggungan keluarga (jiwa).

Menggunakan takaran 2,7 Kg beras/makanan pokok per jiwa.

Total yang harus dibayar dikonversi otomatis ke nilai Rupiah berdasarkan harga beras yang diinputkan.

Zakat Penghasilan (Profesi)

Menghitung zakat dari gaji bulanan, bonus, dikurangi cicilan/hutang jatuh tempo.

Nisab diqiyaskan dengan 85 gram emas per tahun (dibagi 12 untuk nisab bulanan).

Kadar zakat: 2,5%.

Zakat Mata Uang (Nuqud)

Menggabungkan nilai Uang Tunai/Tabungan, Emas tersimpan, dan Perak tersimpan.

Memungkinkan pengguna menyesuaikan harga Emas dan Perak di pasaran saat ini.

Nisab: Setara 85 gram Emas.

Kadar zakat: 2,5%.

Zakat Binatang Ternak (An'am)

Perhitungan otomatis berdasarkan tabel Fikih untuk hewan yang digembalakan (Saimah).

Sapi/Kerbau: Nisab dimulai dari 30 Ekor (Otomatis menghitung jenis Tabi' atau Musinnah yang harus dikeluarkan).

Kambing/Domba: Nisab dimulai dari 40 Ekor (Otomatis menghitung jumlah ekor yang wajib dizakatkan).

Zakat Pertanian

Menghitung zakat dari hasil panen gabah/beras.

Pengguna dapat memilih jenis pengairan: Alami/Tadah Hujan (10%) atau Irigasi Berbayar/Pompa (5%).

Nisab: 653 Kg gabah.

🛠️ Teknologi yang Digunakan

Aplikasi ini sangat ringan dan dibangun menggunakan teknologi web standar:

HTML5: Struktur utama aplikasi.

Vanilla JavaScript: Logika perhitungan zakat, format mata uang, dan interaksi DOM.

Tailwind CSS (via CDN): Framework CSS untuk styling dan desain yang responsif (Mobile-Friendly).

Lucide Icons (via CDN): Ikon SVG ringan untuk mempercantik antarmuka pengguna.

🚀 Cara Menjalankan Aplikasi

Karena aplikasi ini murni berupa file HTML statis, Anda tidak perlu menginstal Node.js, NPM, atau server backend apa pun.

Menjalankan Secara Lokal:

Unduh atau clone repositori ini.

Buka file index.html menggunakan browser web modern apa saja (Chrome, Firefox, Safari, Edge).

Melakukan Deployment (Hosting):

Aplikasi ini sangat mudah untuk di-hosting secara gratis menggunakan layanan seperti GitHub Pages, Netlify, atau Vercel.

Buat repositori baru di GitHub dan unggah file index.html.

Buka Settings > Pages di repositori GitHub Anda.

Pilih branch main atau master dan simpan.

Dalam beberapa menit, aplikasi Kalkulator Zakat Anda sudah online dan dapat diakses!

📖 Referensi Nisab & Ketentuan Dasar (Default)

Nilai-nilai ini dijadikan konstanta default di dalam aplikasi, namun pengguna dapat menyesuaikan harga:

Harga Emas: Rp 1.200.000 / gram

Harga Perak: Rp 15.000 / gram

Nisab Zakat Maal/Mata Uang: 85 gram emas (± Rp 102.000.000)

Nisab Zakat Penghasilan: Rp 102.000.000 / 12 bulan (± Rp 8.500.000 per bulan)

Nisab Zakat Pertanian: 653 Kg

📝 Lisensi

Proyek ini bersifat Open Source. Anda bebas menggunakan, memodifikasi, dan mendistribusikan ulang kode ini untuk keperluan pribadi, lembaga amil zakat, masjid, maupun komunitas.

Dibuat untuk memudahkan umat dalam menunaikan rukun Islam yang ketiga.

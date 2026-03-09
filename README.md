<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Eksplorasi Laporan: Kalkulator Zakat Web</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <!-- Chosen Palette: Islamic Modern Calm (Green #0A9E59, Yellow #FFD000, Cream #F3EBE0, Dark Text #1A1A1A, White) -->
    <!-- Application Structure Plan: The SPA uses a dashboard-style architecture to transform a static README into an interactive learning hub. It begins with a hero section for context, followed by a 'Master-Detail' interactive viewer for the 5 Zakat types (allowing users to focus on one topic at a time without scrolling through a wall of text). A visual data section uses a bar chart to compare Nisab thresholds, providing immediate scale comprehension. Finally, a technical and deployment overview is presented in a card grid. This structure prioritizes guided exploration and chunked information processing over linear reading. -->
    <!-- Visualization & Content Choices: 
        1. Overview -> Goal: Inform -> Hero section with dynamic stat counters -> Justification: Grabs attention and summarizes scope -> HTML/Tailwind.
        2. 5 Zakat Types -> Goal: Organize & Inform -> Master-Detail interactive panel -> Justification: Chunks complex Fiqh rules into digestible, user-selected pieces -> Vanilla JS + Tailwind.
        3. Nisab Defaults -> Goal: Compare -> Horizontal Bar Chart -> Justification: Visually contrasts the massive difference between annual Maal Nisab and monthly Profesi Nisab -> Chart.js.
        4. Tech Stack & Deployment -> Goal: Inform -> Interactive Card Grid with hover states -> Justification: Makes technical documentation scannable -> HTML/Tailwind.
        Confirming NO SVG/Mermaid: Used Unicode emojis exclusively for iconography. 
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
            height: 50vh;
            max-height: 400px;
        }
        @media (max-width: 768px) {
            .chart-container {
                height: 40vh;
                max-height: 300px;
            }
        }
        .fade-in {
            animation: fadeInOpacity 0.4s ease-in forwards;
        }
        @keyframes fadeInOpacity {
            0% { opacity: 0; transform: translateY(10px); }
            100% { opacity: 1; transform: translateY(0); }
        }
        .hide-scrollbar::-webkit-scrollbar {
            display: none;
        }
        .hide-scrollbar {
            -ms-overflow-style: none;
            scrollbar-width: none;
        }
    </style>
</head>
<body class="bg-[#f8fafc] text-[#1A1A1A] font-sans antialiased selection:bg-[#FFD000] selection:text-[#1A1A1A]">

    <nav class="bg-white border-b-4 border-[#FFD000] sticky top-0 z-50 shadow-sm">
        <div class="max-w-6xl mx-auto px-4 py-4 flex justify-between items-center">
            <div class="flex items-center space-x-2">
                <span class="text-2xl">🕌</span>
                <span class="font-bold text-xl text-[#0A9E59]">ZakatApp <span class="text-[#1A1A1A] font-light">Laporan</span></span>
            </div>
            <div class="hidden md:flex space-x-6 font-medium text-sm">
                <button onclick="scrollToSection('beranda')" class="hover:text-[#0A9E59] transition">Beranda</button>
                <button onclick="scrollToSection('jenis-zakat')" class="hover:text-[#0A9E59] transition">Kaidah Zakat</button>
                <button onclick="scrollToSection('referensi-nisab')" class="hover:text-[#0A9E59] transition">Referensi Nisab</button>
                <button onclick="scrollToSection('teknologi')" class="hover:text-[#0A9E59] transition">Teknologi</button>
            </div>
        </div>
    </nav>

    <main class="max-w-6xl mx-auto px-4 py-8 space-y-16">

        <section id="beranda" class="bg-[#0A9E59] rounded-3xl p-8 md:p-12 text-white shadow-xl relative overflow-hidden">
            <div class="absolute top-0 right-0 w-64 h-64 bg-white opacity-5 rounded-full -translate-y-1/2 translate-x-1/4"></div>
            <div class="relative z-10 max-w-3xl">
                <span class="inline-block py-1 px-3 rounded-full bg-[#FFD000] text-[#1A1A1A] text-xs font-bold tracking-wider uppercase mb-4">Laporan Analisis</span>
                <h1 class="text-4xl md:text-5xl font-bold mb-4 leading-tight">Arsitektur & Kaidah: Kalkulator Zakat Web SPA</h1>
                <p class="text-lg text-emerald-100 mb-8 leading-relaxed">
                    Aplikasi ini dirancang untuk memudahkan umat Islam dalam menghitung kewajiban zakat secara akurat dan real-time. Dibangun berlandaskan kaidah Fikih Zakat klasik, beroperasi penuh di sisi klien tanpa memerlukan backend.
                </p>
                <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
                    <div class="bg-white/10 backdrop-blur-sm p-4 rounded-xl border border-white/20">
                        <div class="text-3xl mb-1">⚖️</div>
                        <div class="text-2xl font-bold">5</div>
                        <div class="text-xs text-emerald-200">Jenis Zakat</div>
                    </div>
                    <div class="bg-white/10 backdrop-blur-sm p-4 rounded-xl border border-white/20">
                        <div class="text-3xl mb-1">⚡</div>
                        <div class="text-2xl font-bold">100%</div>
                        <div class="text-xs text-emerald-200">Client-Side</div>
                    </div>
                    <div class="bg-white/10 backdrop-blur-sm p-4 rounded-xl border border-white/20">
                        <div class="text-3xl mb-1">🔄</div>
                        <div class="text-2xl font-bold">API</div>
                        <div class="text-xs text-emerald-200">Sinkronisasi Harga</div>
                    </div>
                    <div class="bg-white/10 backdrop-blur-sm p-4 rounded-xl border border-white/20">
                        <div class="text-3xl mb-1">📖</div>
                        <div class="text-2xl font-bold">Fikih</div>
                        <div class="text-xs text-emerald-200">Kaidah Klasik</div>
                    </div>
                </div>
            </div>
        </section>

        <section id="jenis-zakat">
            <div class="mb-8">
                <h2 class="text-3xl font-bold text-[#1A1A1A] mb-2">Eksplorasi Kaidah Zakat</h2>
                <p class="text-gray-600">Pilih kategori di bawah ini untuk melihat detail aturan, batas nisab, dan kadar perhitungan masing-masing jenis zakat yang diimplementasikan dalam aplikasi.</p>
            </div>

            <div class="flex flex-col md:flex-row gap-6">
                <div class="w-full md:w-1/3 flex flex-col space-y-2" id="zakat-menu">
                </div>
                
                <div class="w-full md:w-2/3">
                    <div class="bg-white rounded-2xl shadow-lg border border-gray-100 p-6 md:p-8 h-full" id="zakat-detail-container">
                        <div class="flex flex-col items-center justify-center h-full text-center text-gray-400 py-12">
                            <span class="text-5xl mb-4">👈</span>
                            <p>Pilih salah satu jenis zakat di samping untuk melihat detailnya.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="referensi-nisab" class="bg-[#F3EBE0] rounded-3xl p-8 md:p-12 shadow-inner">
            <div class="mb-8 text-center max-w-2xl mx-auto">
                <h2 class="text-3xl font-bold text-[#1A1A1A] mb-4">Referensi Nisab Default (Rupiah)</h2>
                <p class="text-gray-700">Visualisasi ini membandingkan ambang batas (Nisab) untuk zakat yang diukur menggunakan standar nilai emas (asumsi Rp 1.200.000/gram). Nilai ini dapat disinkronisasi melalui API pada aplikasi utama.</p>
            </div>
            
            <div class="bg-white p-6 rounded-2xl shadow-md border border-[#E8DCC8]">
                <div class="chart-container">
                    <canvas id="nisabChart"></canvas>
                </div>
                <div class="mt-6 grid grid-cols-1 md:grid-cols-3 gap-4 text-sm text-center">
                    <div class="p-3 bg-gray-50 rounded-lg">
                        <span class="block text-gray-500 mb-1">Harga Emas Default</span>
                        <strong class="text-lg text-[#0A9E59]">Rp 1.200.000 / gr</strong>
                    </div>
                    <div class="p-3 bg-gray-50 rounded-lg">
                        <span class="block text-gray-500 mb-1">Nisab Pertanian</span>
                        <strong class="text-lg text-[#0A9E59]">653 Kg Gabah</strong>
                    </div>
                    <div class="p-3 bg-gray-50 rounded-lg">
                        <span class="block text-gray-500 mb-1">Nisab Ternak</span>
                        <strong class="text-lg text-[#0A9E59]">30 Sapi / 40 Kambing</strong>
                    </div>
                </div>
            </div>
        </section>

        <section id="teknologi">
            <div class="mb-8">
                <h2 class="text-3xl font-bold text-[#1A1A1A] mb-2">Arsitektur & Deployment</h2>
                <p class="text-gray-600">Aplikasi SPA ini dirancang agar ringan, aman (tanpa menyimpan data ke server), dan sangat mudah untuk disebarluaskan.</p>
            </div>

            <div class="grid md:grid-cols-2 gap-8">
                <div class="bg-white rounded-2xl shadow-md border border-gray-100 p-8">
                    <h3 class="text-xl font-bold mb-6 flex items-center"><span class="mr-2">🛠️</span> Teknologi Inti</h3>
                    <ul class="space-y-4">
                        <li class="flex items-start">
                            <span class="bg-[#FFD000] text-[#1A1A1A] rounded p-1 mr-3 mt-1">🌐</span>
                            <div>
                                <strong class="block text-gray-900">HTML5 & Vanilla JavaScript</strong>
                                <span class="text-sm text-gray-600">Membentuk struktur utama dan menangani seluruh logika Fikih, perhitungan matematika, dan interaksi DOM tanpa framework JS berat.</span>
                            </div>
                        </li>
                        <li class="flex items-start">
                            <span class="bg-[#FFD000] text-[#1A1A1A] rounded p-1 mr-3 mt-1">🎨</span>
                            <div>
                                <strong class="block text-gray-900">Tailwind CSS (via CDN)</strong>
                                <span class="text-sm text-gray-600">Memberikan styling modern, tata letak responsif untuk perangkat seluler, tanpa memerlukan proses build lokal.</span>
                            </div>
                        </li>
                        <li class="flex items-start">
                            <span class="bg-[#FFD000] text-[#1A1A1A] rounded p-1 mr-3 mt-1">✨</span>
                            <div>
                                <strong class="block text-gray-900">Ikonografi & UI</strong>
                                <span class="text-sm text-gray-600">Memanfaatkan Lucide Icons yang disuntikkan secara dinamis untuk antarmuka yang bersih dan ramah pengguna.</span>
                            </div>
                        </li>
                    </ul>
                </div>

                <div class="bg-gray-900 text-white rounded-2xl shadow-md p-8">
                    <h3 class="text-xl font-bold mb-6 flex items-center text-[#FFD000]"><span class="mr-2">🚀</span> Panduan Deployment</h3>
                    <p class="text-sm text-gray-300 mb-6">Karena aplikasi berupa file HTML statis tanpa backend, proses hosting sepenuhnya gratis dan instan.</p>
                    
                    <div class="relative border-l-2 border-[#0A9E59] ml-3 space-y-6">
                        <div class="relative pl-6">
                            <div class="absolute w-4 h-4 bg-[#0A9E59] rounded-full -left-[9px] top-1"></div>
                            <strong class="block text-[#FFD000]">1. Siapkan Repositori</strong>
                            <span class="text-sm text-gray-400">Buat repositori baru di GitHub dan unggah file tunggal `index.html`.</span>
                        </div>
                        <div class="relative pl-6">
                            <div class="absolute w-4 h-4 bg-[#0A9E59] rounded-full -left-[9px] top-1"></div>
                            <strong class="block text-[#FFD000]">2. Aktifkan GitHub Pages</strong>
                            <span class="text-sm text-gray-400">Masuk ke menu Settings > Pages. Pilih branch `main` atau `master`.</span>
                        </div>
                        <div class="relative pl-6">
                            <div class="absolute w-4 h-4 bg-[#0A9E59] rounded-full -left-[9px] top-1"></div>
                            <strong class="block text-[#FFD000]">3. Aplikasi Online</strong>
                            <span class="text-sm text-gray-400">Tunggu beberapa menit, Kalkulator Zakat siap diakses oleh umat melalui URL publik.</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <footer class="bg-white border-t border-gray-200 mt-12 py-8 text-center text-sm text-gray-500">
        <p>Proyek Open Source. Dibuat untuk memudahkan umat dalam menunaikan rukun Islam yang ketiga.</p>
    </footer>

    <script>
        const zakatData = [
            {
                id: 'fitrah',
                icon: '👥',
                title: 'Zakat Fitrah',
                shortDesc: 'Kewajiban jiwa di bulan Ramadhan.',
                nisab: 'Tidak ada nisab khusus. Wajib bagi yang memiliki kelebihan makanan.',
                kadar: '2,7 Kg beras/makanan pokok per jiwa.',
                detail: 'Kalkulator ini menghitung berdasarkan jumlah tanggungan keluarga. Total beras yang harus dikeluarkan (dalam Kg) akan dikonversi otomatis ke nilai Rupiah berdasarkan input harga beras di pasaran saat ini.'
            },
            {
                id: 'profesi',
                icon: '💼',
                title: 'Zakat Penghasilan',
                shortDesc: 'Zakat dari gaji dan pendapatan profesi.',
                nisab: 'Diqiyaskan dengan 85 gram emas per tahun (dibagi 12 untuk bulanan).',
                kadar: '2,5% dari penghasilan bersih.',
                detail: 'Aplikasi menghitung total gaji bulanan ditambah bonus, lalu dikurangi cicilan atau hutang yang jatuh tempo pada bulan tersebut. Batas nisab bersifat dinamis, otomatis menyesuaikan pergerakan harga emas.'
            },
            {
                id: 'nuqud',
                icon: '💰',
                title: 'Zakat Mata Uang',
                shortDesc: 'Zakat untuk simpanan emas, perak, dan uang.',
                nisab: 'Setara nilai 85 gram Emas.',
                kadar: '2,5% dari total aset.',
                detail: 'Menggabungkan kalkulasi Uang Tunai/Tabungan, Emas, dan Perak yang tersimpan selama 1 tahun (Haul). Dilengkapi fitur Sinkronisasi Harga API untuk mengambil harga pasar terbaru secara real-time.'
            },
            {
                id: 'ternak',
                icon: '🐄',
                title: 'Zakat Binatang Ternak',
                shortDesc: 'Zakat untuk hewan ternak yang digembalakan.',
                nisab: '30 ekor untuk Sapi/Kerbau, 40 ekor untuk Kambing/Domba.',
                kadar: 'Bervariasi (Tabi\', Musinnah, atau kelipatan ekor).',
                detail: 'Logika aplikasi mengotomatisasi tabel Fikih klasik. Untuk sapi, sistem menentukan apakah yang harus dikeluarkan adalah Tabi\' (umur 1 tahun) atau Musinnah (umur 2 tahun) berdasarkan rentang jumlah ternak.'
            },
            {
                id: 'pertanian',
                icon: '🌾',
                title: 'Zakat Pertanian',
                shortDesc: 'Zakat dari hasil panen tanaman pangan.',
                nisab: '653 Kg gabah (atau 520 Kg beras).',
                kadar: '10% (Alami/Tadah Hujan) atau 5% (Irigasi Berbayar).',
                detail: 'Dikeluarkan setiap kali masa panen. Aplikasi menyediakan *toggle* untuk memilih jenis pengairan lahan yang akan secara otomatis menyesuaikan persentase kadar zakat yang wajib dikeluarkan pengguna.'
            }
        ];

        let activeZakatId = null;

        function initZakatMenu() {
            const menuContainer = document.getElementById('zakat-menu');
            menuContainer.innerHTML = '';

            zakatData.forEach(zakat => {
                const btn = document.createElement('button');
                btn.className = `text-left p-4 rounded-xl border-2 transition-all duration-200 flex items-center space-x-4 ${activeZakatId === zakat.id ? 'border-[#0A9E59] bg-[#0A9E59] text-white shadow-md' : 'border-gray-100 bg-white text-gray-700 hover:border-[#FFD000] hover:bg-gray-50'}`;
                btn.onclick = () => selectZakat(zakat.id);
                
                btn.innerHTML = `
                    <div class="text-3xl">${zakat.icon}</div>
                    <div>
                        <strong class="block text-lg">${zakat.title}</strong>
                        <span class="text-sm opacity-80">${zakat.shortDesc}</span>
                    </div>
                `;
                menuContainer.appendChild(btn);
            });
        }

        function selectZakat(id) {
            activeZakatId = id;
            initZakatMenu(); 
            
            const detailContainer = document.getElementById('zakat-detail-container');
            const data = zakatData.find(z => z.id === id);
            
            detailContainer.innerHTML = `
                <div class="fade-in">
                    <div class="flex items-center space-x-3 mb-6 pb-4 border-b border-gray-100">
                        <span class="text-4xl">${data.icon}</span>
                        <h3 class="text-3xl font-bold text-[#1A1A1A]">${data.title}</h3>
                    </div>
                    
                    <div class="space-y-6">
                        <div class="bg-[#F3EBE0] p-4 rounded-xl border-l-4 border-[#FFD000]">
                            <strong class="block text-sm text-gray-500 uppercase tracking-wider mb-1">Batas Nisab</strong>
                            <span class="text-lg font-medium text-[#1A1A1A]">${data.nisab}</span>
                        </div>
                        
                        <div class="bg-emerald-50 p-4 rounded-xl border-l-4 border-[#0A9E59]">
                            <strong class="block text-sm text-gray-500 uppercase tracking-wider mb-1">Kadar Zakat</strong>
                            <span class="text-lg font-medium text-[#1A1A1A]">${data.kadar}</span>
                        </div>

                        <div>
                            <strong class="block text-sm text-gray-500 uppercase tracking-wider mb-2">Implementasi dalam Aplikasi</strong>
                            <p class="text-gray-700 leading-relaxed bg-white border border-gray-100 p-5 rounded-xl shadow-sm">${data.detail}</p>
                        </div>
                    </div>
                </div>
            `;
        }

        function initChart() {
            const ctx = document.getElementById('nisabChart').getContext('2d');
            
            new Chart(ctx, {
                type: 'bar',
                data: {
                    labels: [
                        ['Nisab Maal & Nuqud', '(Akumulasi 1 Tahun)'], 
                        ['Nisab Profesi', '(Akumulasi 1 Tahun)'], 
                        ['Nisab Profesi', '(Bulanan)']
                    ],
                    datasets: [{
                        label: 'Nilai Nisab (Rupiah)',
                        data: [102000000, 102000000, 8500000],
                        backgroundColor: [
                            'rgba(255, 208, 0, 0.8)',
                            'rgba(10, 158, 89, 0.8)',
                            'rgba(10, 158, 89, 0.4)'
                        ],
                        borderColor: [
                            'rgb(230, 187, 0)',
                            'rgb(8, 130, 73)',
                            'rgb(8, 130, 73)'
                        ],
                        borderWidth: 1,
                        borderRadius: 6
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    indexAxis: 'y',
                    plugins: {
                        legend: { display: false },
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    let label = context.dataset.label || '';
                                    if (label) { label += ': '; }
                                    if (context.parsed.x !== null) {
                                        label += new Intl.NumberFormat('id-ID', { style: 'currency', currency: 'IDR', minimumFractionDigits: 0 }).format(context.parsed.x);
                                    }
                                    return label;
                                }
                            }
                        }
                    },
                    scales: {
                        x: {
                            ticks: {
                                callback: function(value) {
                                    if(value >= 1000000) return 'Rp ' + (value / 1000000) + ' Juta';
                                    return value;
                                },
                                font: { size: 11 }
                            },
                            grid: { color: '#f1f5f9' }
                        },
                        y: {
                            ticks: { font: { size: 12, weight: 'bold' } },
                            grid: { display: false }
                        }
                    }
                }
            });
        }

        function scrollToSection(id) {
            document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
        }

        window.onload = () => {
            initZakatMenu();
            selectZakat('fitrah');
            initChart();
        };
    </script>
</body>
</html>

# **Project Monolith** Game Development Design 

**Overview**  
**\[Konsep Inti\]**   
Farming Simulation 2D Pixel di planet asing, berfokus pada Botani Alien dan Automasi Robotik untuk bertahan hidup dan mengirimkan sinyal "Planet Layak Huni" ke Bumi.

**\[Genre\]**   
Farming, Simulation, Survival (Ringan), Exploration. 

**\[Platform\]**   
PC (Steam, Itch.io) dan Mobile (iOS/Android). 

**\[Target Audience\]**  
Pecinta genre cozy sim (Stardew Valley, Animal Crossing) yang mencari tantangan survival dan Sci-Fi (masih termasuk casual hingga mid-core). Usia 15-35 tahun, semua gender. 

**\[Monetisasi\]**  
Beli Sekali (Premium/Single Purchase) untuk versi PC dan Mobile. Model ini sangat disukai oleh target audiens cozy sim yang menghindari pay-to-win. Potensi DLC/Ekspansi (misalnya, planet baru, set robot baru) untuk pendapatan jangka panjang.

**\[Tujuan Pengembangan\]**  
1\. Menciptakan *Loop Gameplay* yang Inovatif: Menggabungkan *satisfaction* dari *automation* (gaya Factorio) dengan ketenangan *farming* (gaya Stardew Valley). 

2\. Komunitas: Mencapai rating "Sangat Positif" di Steam dan membangun komunitas yang loyal sebelum peluncuran DLC. 

3\. Financial: Mengembalikan biaya pengembangan (*break-even*) dalam 6 bulan pertama setelah rilis.

**Gameplay dan Mekanika**  
**\[Mekanik Inti (Core Mechanics)\]**  
**1\. Botani Eksotis:**  
Mekanik ini adalah jantung dari *farming sim* Anda, dengan fokus pada tantangan ilmiah dan adaptasi lingkungan.

Siklus Tanam dan Analisis: Setiap benih alien yang ditemukan (misalnya, *Crystalfruit*, *Ion-Bloom*, *Sludge-Root*) tidak hanya membutuhkan air, tetapi juga Kondisi Tumbuh Optimal yang harus diidentifikasi pemain. 

Ini melibatkan:  
**\- Analisis Tanah:** Pemain menggunakan *scanner* di Lab Budidaya untuk menentukan kebutuhan mineral, kelembaban, dan potensi pH tanah di plot.

**\- Spektrum Cahaya:** Tanaman akan memiliki preferensi warna cahaya (Merah, Biru, UV). Pemain harus menempatkan Lampu Spektrum Khusus di atas lahan, di mana intensitas cahaya (memanfaatkan sistem light 2D Godot) akan menentukan laju dan kualitas pertumbuhan. Cahaya yang salah dapat menyebabkan tanaman layu atau mutasi yang tidak terduga.

**\- Pupuk Biomass:** Pupuk dibuat dari bahan baku yang dipanen dari flora/fauna liar (*Biomass*). Ada pupuk untuk 1\. pertumbuhan cepat (*Growth-Catalyst*), pupuk untuk 2\. resistensi hama (*Pest-Repellent*), dan pupuk untuk 3\. meningkatkan hasil panen (*Yield-Booster*).

**Mutasi dan Penemuan:** Ketika tanaman ditanam dalam kondisi yang tidak optimal atau terpapar elemen ekstrem (seperti radiasi Badai Ion), ada persentase peluang terjadinya Mutasi Genetik. Mutasi ini dapat menghasilkan varian tanaman baru yang sangat langka dan berharga, yang kemudian dapat di-*lock* sebagai benih permanen melalui riset di Lab.

**2\. Automasi Robotik:**  
Mekanik ini memberikan elemen *puzzle* dan *management* yang sangat menarik bagi audiens *mid-core*.

**\- Drone Fungsional:** Ada Drone spesialis (misalnya, *Dripper-Drone* untuk menyiram, *Collector-Drone* untuk memanen). Setiap Drone memiliki Baterai terbatas dan Memori Program terbatas.

**\- Pemrograman *Path* Sederhana:** Pemain dapat memprogram jalur dasar untuk Drone menggunakan sistem *point-and-click* di antarmuka Godot. Contoh: "Drone A pergi ke Titik Air \> Isi Penuh \> Ikuti *Path* 1 (melewati lahan 1-4) \> Kembali ke Stasiun Pengisian."

**\- Sistem *Auto-Harvester* (Robot Stasioner):** Ini adalah *upgrade* permanen yang ditempatkan di sebelah lahan besar. Berfungsi untuk menyiram, memupuk, dan memanen secara otomatis dalam radius tertentu, tetapi membutuhkan biaya Energi yang sangat besar dan harus sering diperbaiki setelah Badai Ion.

**\- Tantangan AI:** Robot rentan terhadap Badai Ion yang dapat menyebabkan glitch sementara pada AI mereka (misalnya, *Dripper-Drone* menyiram dua kali lipat atau *Collector-Drone* membuang hasil panen di tempat yang salah), memaksa pemain untuk sesekali memeriksa dan memperbaiki sistem automasi.

**3\. Manajemen Sumber Daya:**   
**\- Energi (Listrik):** Diperlukan untuk Lab, Robot, Lampu Spektrum, dan sistem pertahanan. Sumber daya utamanya adalah Panel Surya (stabil, tapi lemah) dan Generator Geotermal/Ion (kuat, tapi berisiko merusak peralatan jika terlalu panas/radiasi). Pemain harus membuat keputusan: Energi tinggi dengan risiko, atau energi rendah dengan stabilitas.

**\- Air:** Sangat vital. Air didapatkan melalui Penyuling Air Atmosfer (lambat) atau Sumur Tanah (cepat, tapi air mungkin tercemar dan perlu Filtrasi di Lab). Kapasitas penyimpanan air harus di-*upgrade* secara teratur.

\- **Suku Cadang/Mineral:** Diperlukan untuk *crafting* *upgrade* dan perbaikan. Suku Cadang Biasa (*scrap metal*) didapatkan dari reruntuhan di zona awal. Mineral Langka (misalnya, *Tiberium Shard*, *Ion Crystal*) hanya dapat ditambang di zona berbahaya (Geotermal/Ionosphere).

**\- Pentingnya *Crafting***: Hampir semua *item* penting—mulai dari Drone hingga *Auto-Harvester* hingga Pupuk—harus dibuat di Lab menggunakan kombinasi Sumber Daya dan Suku Cadang yang dikumpulkan.

**\[Loop Gameplay\]**  
**1\. Mengeksplorasi/Scavenging:**   
**Tujuan:** Mengumpulkan sumber daya non-terbarukan dan pengetahuan baru. Pemain harus keluar dari zona aman (Habitat) menuju Reruntuhan, Zona Geotermal, atau Zona Ionosphere. 

***Aktivitas:***   
1\. Mencari Puing dan Suku Cadang: Penting untuk perbaikan dan *crafting* alat automasi.  
2\. Menambang Mineral Langka: Diperlukan untuk *upgrade* berteknologi tinggi dan riset.  
3\. Menemukan Benih Liar: Mendapatkan benih alien baru.   
4\. Mengumpulkan Bio-Data dan Puing Teknologi: Dibawa kembali ke Lab untuk memulai riset.

**2\. Riset/Crafting:**  
**Tujuan:** Mengubah sumber daya mentah menjadi *upgrade* fungsional dan ilmu pengetahuan. Fase ini adalah *hub* strategis pemain. 

***Aktivitas:***   
1\. Analisis Bio-Data: Investasi *data* yang dikumpulkan dari eksplorasi atau panen untuk membuka *upgrade* di Pohon Riset (misalnya, formula pupuk baru, *blueprints* Drone).   
2\. Pembuatan Pupuk: Mengolah *Biomass* alien menjadi Pupuk Biomass spesifik.   
3\. Perbaikan & Pembuatan Suku Cadang: Menggunakan Mineral dan Puing untuk memperbaiki Drone yang rusak, membuat *part* Drone baru, atau membangun Lampu Spektrum.

**3\. Bertani/Mengelola:**  
**Tujuan:** Memanfaatkan *upgrade* dari Fase 2 untuk menghasilkan panen berkualitas tinggi dan *Bio-Data* lebih banyak, sambil mempertahankan infrastruktur. 

***Aktivitas:***   
1\. Penanaman Strategis: Menanam benih di plot yang paling sesuai dengan kebutuhan Spektrum Cahaya.   
2\. Pemrograman & Pemeliharaan Drone: Mengatur *pathfinding* Drone agar bekerja efisien.   
3\. Manajemen Energi: Mematikan sistem yang tidak perlu, memperbaiki Panel Surya setelah Badai Ion, memastikan daya Generator Geotermal stabil.   
4\. Penanganan Ancaman: Mengaktifkan *Repeller Device* atau memperbaiki pagar setelah serangan Hama Alien.

**4\. Menjual/Tukar:**  
**Tujuan:** Mengkonversi hasil kerja menjadi Credit atau Item Langka untuk mendukung *loop* selanjutnya. 

***Aktivitas:***   
1\. Menjual Hasil Panen: Hasil panen *high-quality* dijual kepada Kapal Dagang NPC (yang tiba secara periodik) untuk mendapatkan Credit.   
2\. Tukar Barang: Membeli Suku Cadang/Mineral yang sangat langka dari pedagang.   
3\. Investasi: Menggunakan Credit untuk membeli *blueprint* non-riset atau membeli benih dasar yang mahal. → *Credit* digunakan untuk membeli bahan bakar atau *upgrade* dasar yang membantu Fase 1 (Eksplorasi) dan Fase 2 (Riset) menjadi lebih efisien.

Memastikan transisi yang mulus antara scene eksplorasi (dunia luar) dan scene pertanian (pangkalan).

**\[Kontrol\]**  
**Mouse & Keyboard (PC)**: Klik untuk bergerak, interaksi (memetik/menggali), dan manajemen *inventory*. Tombol *hotkey* untuk peralatan. 

**Sentuh (Mobile):** Kontrol berbasis sentuh (*tap to move/interact*). Kontrol harus mulus, penting untuk *porting* Godot ke *mobile*.

Menggunakan *input map* Godot yang dapat dikonfigurasi ulang untuk *keyboard* dan *touch event* secara terpisah.

**\[Sistem Progresi\]**  
**Pohon Riset (Tech Tree):** Pemain maju dengan menginvestasikan Bio-Data dan Mineral Langka. Tiga cabang utama: Botani (membuka benih baru, pupuk canggih), Teknologi (membuka *blueprint* Drone dan sistem *automation*), dan Habitat (meningkatkan kapasitas energi dan ketahanan *base*). Tidak ada sistem *leveling* karakter tradisional.

Struktur data *dictionary* atau *JSON* untuk *Tech Tree*. Kondisi *unlock* berdasarkan *item* (data/mineral) yang dikonsumsi, bukan XP.

**\[Sistem Pertarungan\]**  
**Minimalis dan Non-Fatal:** Pertarungan jarang dan berfokus pada pertahanan lahan, bukan *combat* karakter. Ancaman: Hama Alien (makhluk kecil) atau Fauna Agresif yang berkeliaran. Interaksi: Pemain menggunakan Perangkat Pengusir (Repeller Device), Jebakan Sonik, atau Auto-Turret (yang membutuhkan energi) untuk menjaga jarak atau menghalau, bukan membunuh.

Fisika 2D Godot digunakan untuk mendeteksi *collision* hama dengan *defense perimeter*. Fokus pada manajemen *cooldown* alat *repellent*.

**\[AI Systems\]**  
**Robot & Drone (Sekutu):** AI sederhana berbasis *pathfinding* dan *state machine*. Mereka memiliki kondisi kerusakan (saat terkena Badai Ion) yang perlu diperbaiki pemain. 

**Fauna/Hama (Musuh):** AI berbasis *patrol* dan *aggro* (agresi), dipicu jika mendekati lahan panen. Mereka dapat ditarik perhatiannya dengan umpan.

Penggunaan Godot *NavigationAgent2D* untuk Drone. *Finite State Machine* (FSM) sederhana untuk perilaku Hama (Patroli \-\> Menyerang Tanaman \-\> Kabur jika dipicu Repeller).

**Dunia Permainan dan Narasi**  
**\[Setting & Latar Belakang\]**  
*Coming Soon…*

**\[Karakter\]**  
*Coming Soon…*

**\[Cerita Utama / Plot\]**  
*Coming Soon…*

**\[Lore\]**  
*Coming Soon…*

**Level Design**  
**\[Struktur Level\]**  
Dunia diimplementasikan sebagai peta 2D *top-down* yang terbagi menjadi beberapa Zona Eksplorasi diskrit (dapat diakses melalui batas *scene* atau *loading screen*). Pangkalan pemain (Habitat/XenoFarm) berada di zona awal dan berfungsi sebagai *hub* utama. 

Zona lain memiliki *aesthetic* dan tingkat kesulitan yang berbeda: Zona Reruntuhan (tingkat 2, banyak puing), Zona Geotermal (tingkat 3, sumber energi, bahaya panas), dan Zona Ionosphere (tingkat 4, risiko Badai Ion tinggi, material langka).

**\[Peta / Map\]**  
Peta Dunia bersifat Semi-Terbuka. Setiap zona memiliki tata letak *tilemap* unik yang mencakup *choke point* (jalur sempit), sumber daya (node tambang), dan Landmark (misalnya, Stasiun Penelitian Lama, Reruntuhan Kapal Kargo) tempat pemain dapat menemukan *blueprint* atau *item quest*. 

Peta pangkalan pemain harus mudah diperluas, memungkinkan *tilemap* lahan pertanian tumbuh secara horizontal atau vertikal seiring kemajuan (*Habitat Upgrade*).

**\[Pencapaian Kunci / Milestone\]**  
Pencapaian ini berfungsi sebagai tujuan jangka panjang yang mendorong eksplorasi dan riset:   
1\. Membangun Sumber Energi Mandiri (misalnya, Turbin Ion pertama).   
2\. Meneliti dan Memanen *Super-Crop* (tanaman alien paling langka).   
3\. Mengaktifkan Sistem Automasi Penuh (semua lahan utama diurus oleh robot).   
4\. Menyelesaikan Pohon Riset Teknologi (mendapatkan *blueprint* Pemancar Sinyal).   
5\. Mengirim Sinyal Evakuasi/Laporan Botani (tujuan akhir).

**\[Tantangan\]**  
1\. Eksistensial (Survival): Manajemen Energi dan air yang konstan; pemain harus menjaga agar sistem pendukung kehidupan (dan robot) tetap berjalan.   
2\. Lingkungan: Badai Ion yang acak (merusak peralatan) dan suhu ekstrem yang memaksa pemain mengembangkan teknologi adaptasi lahan (*shielding*).   
3\. Logistics/Inventory: Keterbatasan ruang penyimpanan di awal, memaksa pemain membuat keputusan sulit tentang material mana yang harus dibawa kembali dari eksplorasi.

**\[Seni dan Audio\]**  
**\[Gaya Seni (Art Style)\]**  
16-bit Sci-Fi Nostalgia: Menggunakan gaya pixel art 16-bit (mirip SNES/Genesis) dengan palet warna yang kaya dan bersemangat. Fokus utama adalah pada efek pencahayaan dinamis (menggunakan sistem *light* 2D Godot) untuk menonjolkan flora dan teknologi yang bioluminescent (bercahaya biru, *cyan*, dan ungu neon) di tengah kegelapan luar angkasa. 

Desain karakter dan *asset* harus memiliki perpaduan antara teknologi futuristik yang bersih dan peralatan yang terlihat usang/berkarat (mencerminkan tema *scavenging* dan *survival*).

**\[UI/UXDesain User Interface\]**  
Holografik & Fungsional: Menggunakan antarmuka bergaya konsol komputer fiksi ilmiah, dengan elemen transparan, *font* yang bersih, dan efek *scanline* halus. UX harus memprioritaskan fungsi *drag-and-drop* untuk *inventory* dan sistem *automation* (memprogram drone). 

Jendela Lab Budidaya harus menyajikan data dan statistik dengan jelas (misalnya, grafik pertumbuhan tanaman, status energi). Tujuannya adalah membuat UI terasa imersif namun tetap minimalis agar tidak menutupi keindahan pixel art.

**\[Musik\]**  
Ambient Sci-Fi Melankolis: Musik utama harus tenang, atmosferik, dan menggunakan banyak *synthesizer* yang menciptakan perasaan keterasingan (kesepian) namun juga harapan. 

*Track* harus berganti berdasarkan lokasi atau ancaman: musik synthwave yang ritmis di pangkalan, *track* ambient yang gelap dan sunyi saat eksplorasi reruntuhan, dan musik yang lebih intens saat terjadi Badai Ion atau ada ancaman Fauna. Efek suara (SFX) harus berfokus pada dengungan peralatan, *beep* robot, dan suara *whoosh* fiksi ilmiah.

**\[Teknis dan Produksi\]**  
**\[Mesin Game (Engine)\]**  
Godot Engine (Versi 4.x atau terbaru): Dipilih karena kinerja 2D yang sangat baik, *cross-platform* yang kuat (PC dan Mobile), sistem *light* 2D yang canggih (penting untuk efek *bio-luminescent*), dan lisensi MIT yang ramah. Godot berjalan sangat baik di Arch Linux.

**\[Bahasa Pemrograman\]**  
GDScript: Bahasa *scripting* utama Godot. Dipilih karena sintaksisnya yang mirip Python, kurva pembelajaran yang rendah, dan integrasi yang erat dengan *engine*. Potensi C\#: Mungkin digunakan untuk bagian *performance-critical* tertentu, seperti simulasi *pathfinding* AI Drone yang kompleks (jika GDScript terbukti menjadi *bottleneck*).

**\[Target Sistem Spesifikasi Untuk Audiens\]**  
**\- Sistem Spesifikasi (Minimum):**  
**Tujuan**: Memungkinkan audiens yang lebih luas (termasuk laptop lama atau PC *budget*) untuk menjalankan game pada pengaturan rendah hingga sedang.   
**OS**: Windows 10 (64-bit), macOS X 10.13+, Linux (termasuk Arch).   
**CPU**: Dual-Core 2.0 GHz (misalnya, Intel Core i3 Gen-3 atau setara AMD).   
**RAM**: 4 GB. GPU: Terintegrasi (Intel HD Graphics 4000\) atau dedicated yang mendukung OpenGL 3.3 / Vulkan 1.0.   
**Penyimpanan**: 500++ MB ruang tersedia.

**\- Sistem Spesifikasi (Rekomendasi):**  
**Tujuan**: Memberikan pengalaman optimal dengan semua efek visual (cahaya, *shader* sederhana) diaktifkan, serta mendukung *scene* eksplorasi yang lebih besar dan sistem *automation* yang kompleks tanpa *lag*.   
**OS**: Windows 10 (64-bit), macOS X 10.14+, Linux (termasuk Arch).   
**CPU**: Quad-Core 3.0 GHz (misalnya, Intel Core i5 Gen-6 atau setara AMD).   
**RAM**: 8 GB. GPU: Dedicated (misalnya, Nvidia GTX 700 series atau AMD R9 280 series) dengan VRAM 2 GB, mendukung Vulkan 1.2+.   
**Penyimpanan**: 1 GB SSD ruang tersedia.

**\[Tools Pengembangan\]**  
**Pixel Art**: Aseprite (standar industri untuk pixel art, sering tersedia melalui AUR di Arch Linux) atau GIMP / Krita (alternatif *open-source*).   
**Audio:** Audacity untuk editing SFX dan LMMS atau Reaper untuk komposisi musik (kedua *tool* ini berfungsi baik di Linux).   
**Kontrol Versi**: Git dengan repositori di GitLab/GitHub, dikelola melalui *command line* atau *GUI client* (misalnya, GitKraken).
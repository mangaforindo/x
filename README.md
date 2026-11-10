# 📚 Manga4indo - Website Baca Manga Online Jam-Free & Serverless

Website baca manga, manhwa, dan komik online Bahasa Indonesia yang sangat ringan, **100% Gratis Hosting**, dan menggunakan sistem **Jamstack Modern**. Website ini memanfaatkan **GitHub Pages** sebagai penyedia hosting statis dan **Google Sheets (CSV)** sebagai CMS (Content Management System) otomatis.

## 🚀 Fitur Utama
- **Google Sheets CMS:** Tambah judul komik baru atau update chapter baru cukup lewat Google Sheets tanpa perlu menyentuh coding di GitHub.
- **Sistem Baca Per Halaman:** Tampilan membaca interaktif satu per satu halaman dengan tombol navigasi *Next*, *Prev*, dan *Click Image to Next*.
- **Dropdown Chapter Selector:** Pindah chapter secara instan langsung dari halaman pembaca atas maupun bawah.
- **Smart Utility Bar:** Dilengkapi dengan fitur **Dark/Light Mode** serta sistem **Bookmark (Simpan Halaman)** berbasis *Local Storage* browser.
- **Anti-Gagal & Kebal Cache:** Dilengkapi sistem *cache-busting* otomatis agar update dari Google Sheets langsung muncul seketika di website.
- **Responsive Design:** Tampilan adaptif yang nyaman dibaca melalui layar HP (Mobile) maupun PC/Laptop.

---

## 📁 Struktur Folder Repositori
```text
mangaforindo/x/
│
├── index.html          # Halaman Utama (Katalog Cover Komik)
├── manga.html          # Halaman Perantara (Daftar Chapter Komik)
├── baca.html           # Halaman Pembaca Utama (Gambar per halaman)
│
├── covers/             # Folder khusus menyimpan gambar cover komik
│   ├── dragon-ball-cover.jpg
│   └── tensei-goblin-cover.jpg
│
└── manga/              # Folder utama konten komik
    ├── dragon-ball/
    │   ├── chapter-01/ # Folder chapter (Penamaan bebas: chapter-1, chapter-1000)
    │   │   ├── 001.jpg # File gambar wajib 3 digit (001.jpg s/d 999.jpg)
    │   │   └── 002.jpg
    │   └── chapter-02/
    └── tensei-goblin/
```

---

## 📊 Panduan Mengelola Google Sheets (CMS)
Dokumen Google Sheet Anda menggunakan 2 tab utama yang wajib dipublikasikan ke web sebagai **CSV**:

### 1. Tab `manga` (Untuk Halaman Utama)
Digunakan untuk mendaftarkan judul komik baru agar muncul di katalog depan.
* **Format Header (Baris 1):** `Key,Judul,Cover`
* **Contoh Pengisian:**

  | Key | Judul | Cover |
  | :--- | :--- | :--- |
  | dragon-ball | Dragon Ball | ../covers/dragon-ball-cover.jpg |
  | tensei-goblin | Tensei Goblin dakedo Shitsumon Aru? | ../covers/tensei-goblin-cover.jpg |

### 2. Tab `chapters` (Untuk Daftar & Dropdown Halaman Baca)
Digunakan untuk memasukkan chapter baru pada komik yang sudah terdaftar.
* **Format Header (Baris 1):** `MangaKey,ChapterId,ChapterName,TotalPages`
* **Contoh Pengisian:**

  | MangaKey | ChapterId | ChapterName | TotalPages |
  | :--- | :--- | :--- | :--- |
  | dragon-ball | chapter-01 | Chapter 01: Bulma dan Son Goku | 37 |
  | dragon-ball | chapter-02 | Chapter 02: Munculnya Kamehameha | 2 |

---

## 🛠️ Aturan Penting Upload Konten Baru

1. **Penamaan Gambar Halaman:** Wajib menggunakan format **3 digit** (`001.jpg`, `009.jpg`, `010.jpg`, `100.jpg`) agar urutan pembaca halaman tidak berantakan.
2. **Sinkronisasi Key:** Teks pada kolom `Key` (di tab manga) harus sama persis dengan kolom `MangaKey` (di tab chapters) serta nama folder komik Anda di GitHub (Gunakan huruf kecil dan tanda strip, contoh: `dragon-ball`).
3. **TotalPages:** Selalu isi kolom `TotalPages` di Google Sheets sesuai dengan jumlah persis file gambar di dalam folder chapter tersebut agar navigasi tombol *Next* tidak error.

---

## 🌐 Lisensi & Kontribusi
Proyek ini dibangun secara open-source. Anda bebas melakukan *forking*, memodifikasi gaya tampilan CSS, atau menggunakannya untuk keperluan koleksi komik pribadi Anda. 

*Selamat Membaca!* 📚

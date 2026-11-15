# Referensi Portofolio Web

Folder ini berisi **dua contoh website portofolio** yang dibuat hanya dengan HTML, CSS, dan JavaScript. Tidak pakai framework, tidak perlu install apa pun.

Dua contoh ini beda bentuk. Pilih **salah satu**, tidak perlu dipakai dua-duanya.

| Contoh        | Bentuk mini proyek                          | Jumlah file |
| ------------- | ------------------------------------------- | ----------- |
| `one-page/`   | Mini game (kuis, memory, tebak angka)       | 1 file HTML |
| `multi-page/` | Halaman website biasa (todo, berita, cuaca) | 4 file HTML |

Nama, foto, dan isi di dalamnya masih data contoh. Ganti dengan data kamu sendiri sebelum dikumpulkan.

---

## Isi Folder

```
Portofolio Refrensi/
├── README.md
├── one-page/
│   └── index.html       -> portofolio 1 file, proyeknya mini game
└── multi-page/
    ├── index.html       -> halaman utama portofolio
    ├── todo.html        -> proyek 1: daftar tugas
    ├── berita.html      -> proyek 2: portal berita
    └── cuaca.html       -> proyek 3: info cuaca
```

---

## Pilih yang Mana?

**Pakai `one-page/index.html` kalau:**

- Mini proyekmu berupa game atau sesuatu yang bisa dimainkan.
- Mau dikumpulkan dalam satu file, jadi tidak ada file yang tertinggal.
- Tidak masalah file HTML-nya panjang karena CSS dan JS ditulis di file yang sama.

**Pakai `multi-page/` kalau:**

- Mini proyekmu berupa halaman website seperti berita, cuaca, katalog, atau todo list.
- Mau terlihat seperti website asli yang punya beberapa halaman.
- Ingat: semua file harus ikut dikumpulkan dan tetap satu folder. Kalau satu file hilang, link proyeknya rusak.

---

## Cara Membuka

1. Buka foldernya.
2. Klik dua kali `index.html` (yang ada di dalam `one-page/` atau `multi-page/`).
3. Website langsung terbuka di browser.

Kalau foto profil tidak muncul, cek koneksi internet. Foto contoh diambil dari Pexels, jadi butuh internet.

Kalau mau lebih aman saat presentasi, jalankan lewat server lokal:

```bash
cd "Portofolio Refrensi"
python3 -m http.server 8000
```

Lalu buka `http://localhost:8000/one-page/` atau `http://localhost:8000/multi-page/`.

---

## 1. `one-page/index.html` — Portofolio Satu File

Semua isi website ada di file ini: CSS di dalam `<style>`, JavaScript di dalam `<script>`. Tidak ada file lain.

Bagian halamannya:

- **Tentang**: perkenalan singkat dan foto profil.
- **Skills**: daftar kemampuan yang ditampilkan sebagai list, bukan persentase.
- **Proyek**: tiga kartu mini game. Kalau diklik, game terbuka di jendela modal tanpa pindah halaman.
- **Kontak**: email, LinkedIn, dan GitHub.
- **Navigasi**: menu berubah jadi tombol garis tiga saat dibuka di HP.

Mini game yang tersedia:

| Game         | Cara main                                             |
| ------------ | ----------------------------------------------------- |
| Kuis Kilat   | 5 soal pilihan ganda, skor dihitung otomatis          |
| Memory Match | 8 pasang emoji, dibalik dan dicocokkan                |
| Tebak Angka  | Tebak angka 1–100, dapat petunjuk terlalu besar/kecil |

**Cara menambah game baru:**

1. Tambah kartu di bagian `#proyek`, ikuti pola yang sudah ada:
   ```html
   <div class="game-card" data-game="gamebaru">
     <div class="game-icon">🎲</div>
     <h3>Judul Game</h3>
     <p>Penjelasan singkat.</p>
     <span class="play">▶ Mainkan</span>
   </div>
   ```
2. Di JavaScript, cari fungsi `openGame()` lalu tambah cabang:
   ```js
   else if (type === "gamebaru") startGameBaru();
   ```
3. Buat fungsi `startGameBaru()` yang mengisi `gameArea.innerHTML`.

---

## 2. `multi-page/` — Portofolio Banyak File

Halaman utama (`index.html`) berisi profil, skill, dan kartu proyek. Setiap kartu membuka file HTML sendiri.

| File          | Isi                                                                                                                                                  |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| `index.html`  | Halaman utama: tentang, skill, daftar proyek, kontak                                                                                                 |
| `todo.html`   | Daftar tugas: tambah tugas + prioritas, filter Semua/Belum/Selesai, hapus tugas, data disimpan di `localStorage`                                     |
| `berita.html` | Portal berita: filter kategori (Teknologi, Bisnis, Gaya Hidup, Sains), headline utama, daftar artikel. Isi berita masih ditulis manual di JavaScript |
| `cuaca.html`  | Info cuaca: cari kota (Bandung, Jakarta, Yogyakarta, Surabaya, Medan), tampil suhu dan prakiraan 5 hari. Datanya masih contoh, bukan dari API        |

Setiap halaman proyek punya link **← Kembali ke Portofolio** di bagian atas.

**Cara menambah proyek baru:**

1. Buat file baru, misalnya `profil.html`. Bisa copy `todo.html` lalu ubah isinya.
2. Tambah kartu di `index.html`, ikuti pola yang ada:
   ```html
   <a class="project-card" href="profil.html">
     <div class="thumb t1">👤</div>
     <div class="project-body">
       <h3>Judul Proyek</h3>
       <p>Penjelasan singkat proyek.</p>
       <span class="project-link">Buka Proyek →</span>
     </div>
   </a>
   ```
3. Jangan lupa tambahkan link balik ke `index.html` di halaman baru.

---

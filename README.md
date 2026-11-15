# Referensi Portofolio Web

Folder ini berisi **dua contoh website portofolio** yang dibuat hanya dengan HTML, CSS, dan JavaScript. Tidak pakai framework, tidak perlu install apa pun.

Dua contoh ini beda bentuk. Pilih **salah satu**, tidak perlu dipakai dua-duanya.

| Contoh | Bentuk mini proyek | Jumlah file |
|---|---|---|
| `spa/` | Mini game (kuis, memory, tebak angka) | 1 file HTML |
| `multi-page/` | Halaman website biasa (todo, berita, cuaca) | 4 file HTML |

Nama, foto, dan isi di dalamnya masih data contoh. Ganti dengan data kamu sendiri sebelum dikumpulkan.

---

## Isi Folder

```
Portofolio Refrensi/
├── README.md
├── spa/
│   └── index.html       -> portofolio 1 file, proyeknya mini game
└── multi-page/
    ├── index.html       -> halaman utama portofolio
    ├── todo.html        -> proyek 1: daftar tugas
    ├── berita.html      -> proyek 2: portal berita
    └── cuaca.html       -> proyek 3: info cuaca
```

---

## Pilih yang Mana?

**Pakai `spa/index.html` kalau:**
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
2. Klik dua kali `index.html` (yang ada di dalam `spa/` atau `multi-page/`).
3. Website langsung terbuka di browser.

Kalau foto profil tidak muncul, cek koneksi internet. Foto contoh diambil dari Pexels, jadi butuh internet.

Kalau mau lebih aman saat presentasi, jalankan lewat server lokal:

```bash
cd "Portofolio Refrensi"
python3 -m http.server 8000
```

Lalu buka `http://localhost:8000/spa/` atau `http://localhost:8000/multi-page/`.

---

## 1. `spa/index.html` — Portofolio Satu File

Semua isi website ada di file ini: CSS di dalam `<style>`, JavaScript di dalam `<script>`. Tidak ada file lain.

Bagian halamannya:

- **Tentang**: perkenalan singkat dan foto profil.
- **Skills**: daftar kemampuan yang ditampilkan sebagai list, bukan persentase.
- **Proyek**: tiga kartu mini game. Kalau diklik, game terbuka di jendela modal tanpa pindah halaman.
- **Kontak**: email, LinkedIn, dan GitHub.
- **Navigasi**: menu berubah jadi tombol garis tiga saat dibuka di HP.

Mini game yang tersedia:

| Game | Cara main |
|---|---|
| Kuis Kilat | 5 soal pilihan ganda, skor dihitung otomatis |
| Memory Match | 8 pasang emoji, dibalik dan dicocokkan |
| Tebak Angka | Tebak angka 1–100, dapat petunjuk terlalu besar/kecil |

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

| File | Isi |
|---|---|
| `index.html` | Halaman utama: tentang, skill, daftar proyek, kontak |
| `todo.html` | Daftar tugas: tambah tugas + prioritas, filter Semua/Belum/Selesai, hapus tugas, data disimpan di `localStorage` |
| `berita.html` | Portal berita: filter kategori (Teknologi, Bisnis, Gaya Hidup, Sains), headline utama, daftar artikel. Isi berita masih ditulis manual di JavaScript |
| `cuaca.html` | Info cuaca: cari kota (Bandung, Jakarta, Yogyakarta, Surabaya, Medan), tampil suhu dan prakiraan 5 hari. Datanya masih contoh, bukan dari API |

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

## Bagian yang Wajib Diganti

Sebelum dikumpulkan, ganti bagian ini:

1. **Nama dan teks perkenalan**
   - Di `spa/index.html`, cari nama "Raka Ardiansyah".
   - Di `multi-page/index.html`, cari nama "Nadira Puspitasari".
   - Ganti juga `@example.com` dan akun LinkedIn/GitHub contoh.

2. **Foto profil**
   - Kedua contoh masih memakai foto stok dari Pexels.
   - Cara paling aman: simpan fotomu di folder yang sama, misalnya `foto.jpg`, lalu ganti bagian `src`:
     ```html
     <img class="portrait" src="foto.jpg" alt="Foto profil saya" />
     ```
   - Di `spa/index.html`, class-nya `avatar`, bukan `portrait`.

3. **Skills**
   - Tulis hanya yang benar-benar bisa kamu pakai. Jangan tulis React atau framework lain kalau belum dipakai.

4. **Daftar proyek**
   - Sesuaikan judul dan deskripsi dengan proyek yang kamu buat sendiri.
   - Jangan bilang "ambil data dari API" kalau datanya masih contoh.

5. **Tahun di footer**
   - Ganti `2025` sesuai tahun kamu.

6. **Link kontak**
   - Pastikan email, LinkedIn, dan GitHub bisa dibuka.

---

## Cara Ganti Warna

Warna diatur di bagian `:root` paling atas CSS. Cukup ganti kode warnanya.

Untuk `multi-page/`:

```css
:root {
  --bg: #f7f5f0;        /* warna latar halaman */
  --card: #ffffff;      /* warna kartu */
  --ink: #1a1a1a;       /* warna teks utama */
  --accent: #c2410c;    /* warna aksen (tombol, link) */
  --border: #e8e3db;    /* warna garis tepi */
}
```

Untuk `spa/`:

```css
:root {
  --bg: #0e1116;
  --card: #161b22;
  --accent: #5eead4;
  --text: #e6edf3;
  --muted: #8b949e;
  --border: #232a33;
}
```

Kode warna diawali `#` dan terdiri dari 6 karakter. Contoh: `#ff0000` merah, `#2563eb` biru.

---

## Catatan Penting

- **Tidak ada database.** Data todo di `multi-page/todo.html` hanya disimpan di browser lewat `localStorage`. Kalau dibuka di browser lain, datanya tidak ikut.
- **Data masih contoh.** Berita ditulis manual, cuaca memakai angka contoh dan acak. Belum ada API.
- **Foto butuh internet.** Kalau ingin aman saat presentasi tanpa internet, ganti dengan foto dari file lokal.
- **Jangan pisahkan file `multi-page/`.** Semua file harus tetap satu folder karena saling terhubung lewat link.
- **Cek di HP juga.** Perkecil lebar browser atau buka lewat HP untuk memastikan tampilan tidak berantakan.

---

## Ide Pengembangan

Kalau ingin nilainya lebih bagus, coba tambahkan salah satu:

- Ganti data cuaca contoh dengan API asli (misalnya Open-Meteo, tidak perlu API key).
- Tambah fitur edit tugas di `todo.html`.
- Tambah kategori atau pencarian di `berita.html`.
- Simpan skor tertinggi game kuis di `localStorage`.
- Tambah mode terang/gelap.

---

## Checklist Sebelum Dikumpulkan

- [ ] Nama, foto, dan teks sudah diganti
- [ ] Tidak ada lagi tulisan `example.com`
- [ ] Semua kartu proyek bisa dibuka
- [ ] Link "Kembali ke Portofolio" berfungsi
- [ ] Tampilan dicek di HP
- [ ] Tidak ada error di Console browser (buka dengan F12)

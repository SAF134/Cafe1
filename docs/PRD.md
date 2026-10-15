# Dokumen Kebutuhan Produk: Website Landing Page [Nama Cafe]

## Gambaran Umum Produk

**Visi Produk:** Website landing page yang hangat, cepat, dan mobile-first, yang membuat pengunjung tertarik datang ke Cafe dengan melihat menu, suasana, dan lokasi dalam satu tempat.

**Target Pengguna:**

- Utama: warga sekitar, mahasiswa, dan pekerja remote (18–35 th) yang mencari tempat ngopi/nongkrong.
- Sekunder: wisatawan dan pengunjung baru yang menemukan Cafe lewat Google Maps/Instagram.

**Tujuan Bisnis:** Meningkatkan kunjungan ke Cafe dan menjadi "etalase digital" yang menggantikan brosur/menu cetak.

**Metrik Keberhasilan:**

- Klik tombol "Petunjuk Arah" dan "WhatsApp" ≥ 10% dari total pengunjung.
- Skor Lighthouse mobile ≥ 90 (Performance, Accessibility, SEO).
- Rata-rata durasi sesi ≥ 45 detik.

## Persona Pengguna

### Persona 1: Raka (Mahasiswa/Pekerja Remote)

- **Demografi:** 22–30 th, mahasiswa/freelancer, melek teknologi.
- **Tujuan:** Mencari tempat nyaman untuk kerja/belajar (Wi-Fi, colokan, harga terjangkau).
- **Kendala/Masalah:** Sulit tahu fasilitas dan harga sebelum datang.
- **Perjalanan Pengguna:** Buka dari Instagram → lihat Fasilitas → cek Menu & harga → klik Petunjuk Arah.

### Persona 2: Sari (Pengunjung Baru/Keluarga)

- **Demografi:** 28–45 th, pekerja/ibu rumah tangga, kemahiran teknis dasar.
- **Tujuan:** Mencari tempat santai untuk bertemu teman/keluarga.
- **Kendala/Masalah:** Ragu soal suasana, jam buka, dan cara menghubungi Cafe.
- **Perjalanan Pengguna:** Cari di Google → lihat Galeri → cek jam buka di Lokasi → chat via WhatsApp.

## Kebutuhan Fitur

| Fitur                | Deskripsi                                                                       | User Story                                                              | Prioritas  | Kriteria Penerimaan                                                                                                                                                        | Dependensi |
| -------------------- | ------------------------------------------------------------------------------- | ----------------------------------------------------------------------- | ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| **Navigasi**         | Navbar sticky dengan 6 menu + tombol menu mobile                                | Sebagai pengguna, saya ingin berpindah antar bagian dengan cepat        | Must       | Smooth scroll ke tiap bagian; menu aktif bertanda saffron; transparan di atas hero, solid Onyx Warm setelah hero; hamburger berfungsi di mobile                            | -          |
| **Beranda (Hero)**   | Hero full-bleed: foto gelap beroverlay, wordmark nama Cafe, tagline, tombol CTA | Sebagai pengunjung, saya ingin langsung paham Cafe ini dan ajakannya    | Must       | Wordmark uppercase besar; dua label meta (mis. "MELAYANI [KOTA]" & "SEJAK [TAHUN]"); tagline; 2 CTA ghost outlined ("Lihat Menu", "Petunjuk Arah") tampil di layar pertama | Navigasi   |
| **Fasilitas**        | Grid kartu fasilitas (ikon + judul + deskripsi singkat)                         | Sebagai pengunjung, saya ingin tahu fasilitas yang tersedia             | Must       | Minimal 6 kartu (mis. Wi-Fi, AC, Colokan, Parkir, Musala, Outdoor); responsif 1/2/3 kolom                                                                                  | -          |
| **Menu**             | Daftar menu per kategori dengan tab filter, data dari `menu.json`               | Sebagai pengunjung, saya ingin melihat menu dan harga                   | Must       | Kategori (Kopi, Non-Kopi, Makanan, Camilan); tiap item: nama, deskripsi, harga (format Rp), foto opsional; filter tanpa reload                                             | -          |
| **Lokasi**           | Google Maps embed, alamat, jam buka, tombol petunjuk arah                       | Sebagai pengunjung, saya ingin tahu cara ke Cafe dan jam bukanya        | Must       | Peta tampil; alamat & jam buka per hari; tombol membuka Google Maps; tombol salin alamat                                                                                   | -          |
| **Galeri**           | Grid foto dengan lightbox                                                       | Sebagai pengunjung, saya ingin melihat suasana dan produk               | Should     | 8–12 foto, lazy-load; klik membuka lightbox; navigasi prev/next & tutup via Esc                                                                                            | -          |
| **Kontak**           | Info kontak + tombol WhatsApp, tautan Instagram                                 | Sebagai pengunjung, saya ingin menghubungi Cafe dengan cepat            | Must       | Tombol WhatsApp (`wa.me`) dengan pesan prefilled; tautan Instagram; tanpa formulir                                                                                         | -          |
| **Footer**           | Hak cipta, tautan cepat, sosial media                                           | Sebagai pengguna, saya ingin navigasi dan info singkat di bawah halaman | Should     | Tampil di semua ukuran layar                                                                                                                                               | -          |
| **SEO & Share**      | Meta tag, Open Graph, schema.org `CafeOrCoffeeShop`                             | Sebagai pemilik, saya ingin Cafe mudah ditemukan di Google              | Should     | Title/description unik; OG image; JSON-LD valid                                                                                                                            | -          |
| **Pemesanan online** | Pesan/bayar lewat website                                                       | -                                                                       | Won't (v1) | -                                                                                                                                                                          | -          |

## Alur Pengguna (User Flows)

### Alur 1: Menemukan Cafe dan Datang

1. Pengguna membuka website (dari Instagram/Google).
2. Melihat Hero, lalu scroll ke Fasilitas dan Menu.
3. Pindah ke Lokasi dan klik "Petunjuk Arah".

- Jalur alternatif: klik CTA "Lihat Menu" di Hero → langsung ke Menu.
- Kondisi error: peta gagal dimuat → tampilkan alamat teks dan tautan Google Maps.

### Alur 2: Menghubungi Cafe

1. Pengguna membuka bagian Kontak.
2. Klik tombol WhatsApp.
3. Aplikasi/WhatsApp Web terbuka dengan pesan prefilled.

- Jalur alternatif: klik tautan Instagram.
- Kondisi error: WhatsApp tidak terpasang → tautan tetap terbuka di WhatsApp Web; tampilkan juga nomor teks agar bisa disalin.

## Kebutuhan Non-Fungsional

### Performa

- **Waktu Muat (Load Time):** LCP < 2,5 detik pada 4G.
- **Pengguna Bersamaan:** Hingga ±500 (situs statis via CDN).
- **Waktu Respons:** Interaksi UI < 100 ms.

### Keamanan

- **Autentikasi:** Tidak diperlukan (situs publik).
- **Otorisasi:** Tidak ada; tanpa area admin.
- **Perlindungan Data:** HTTPS wajib; tidak ada formulir sehingga tidak ada data pengguna yang dikumpulkan.

### Kompatibilitas

- **Perangkat:** Smartphone, tablet, desktop.
- **Browser:** 2 versi terbaru Chrome, Safari, Firefox, Edge.
- **Ukuran Layar:** 360px – 1920px (mobile-first; breakpoint 640/768/1024/1280).

### Aksesibilitas

- **Tingkat Kepatuhan:** WCAG 2.1 AA.
- **Persyaratan Khusus:** HTML semantik, alt text semua gambar, kontras teks ≥ 4,5:1 (lihat penyesuaian warna di Sistem Desain), navigasi keyboard, fokus terlihat, hormati `prefers-reduced-motion`.

## Spesifikasi Teknis

### Frontend

- **Stack Teknologi:** HTML5, Tailwind CSS (CDN atau build via Vite), JavaScript vanilla (ES6). Tanpa framework berat.
- **Sistem Desain:** Ikuti `DESIGN.md` ("spiced parchment gallery") sebagai sumber kebenaran visual; salin token dari bagian _Quick Start_ (Tailwind v4 `@theme`). Ringkasan:
  - **Warna:** kanvas Parchment `#d8cbb8`; teks Onyx Warm `#2c2c2c`; hairline `#b6ab9c`; permukaan gelap `#292622`/`#2c2c2c`; satu-satunya aksen Saffron `#d49653` (bintang, state aktif, maks. 2–3 titik per layar).
  - **Tipografi:** judul serif ringan (300), uppercase, tracking rapat; isi sans 500 14–15px. Pengganti font gratis: TT Ramillas → Cormorant Garamond 300; Satoshi → Satoshi (Fontshare) atau Inter/DM Sans.
  - **Bentuk:** kartu & kontainer radius 0; tombol/tag/input 3px; tanpa shadow; tanpa gradient CSS (kecuali overlay gelap di atas foto); pemisah section hairline 1px.
  - **Tombol:** hanya ghost outlined atau teks, tanpa tombol berwarna solid (termasuk tombol WhatsApp).
  - **Layout:** full-bleed, teks rata kiri; jarak antar section 120–160px (desktop), 64–80px (mobile).
  - **Gerak:** hover/reveal 0,4s ease; marquee nama menu andalan (27s linear) satu-satunya gerak berkelanjutan; tanpa parallax atau animasi scroll.
  - **Citra:** foto atmosferik gelap & hangat setinggi meja, tanpa foto orang; ikon garis tipis 1px.
  - **Penyesuaian atas DESIGN.md:** (1) teks bermakna wajib Onyx `#2c2c2c` di atas parchment; Walnut `#978e81` (kontras ±2:1) dan Espresso `#615b53` (±4,2:1) hanya untuk teks dekoratif/besar, agar lolos WCAG AA; (2) ukuran display (wordmark 199px, heading 115px) diskalakan dengan `clamp()` di mobile (mis. wordmark ≥ 56px, heading ≥ 36px).
- **Desain Responsif:** Mobile-first; grid 1 kolom (mobile), 2 (tablet), 3 (desktop).

### Backend

- **Stack Teknologi:** Tidak ada (situs statis).
- **Persyaratan API:** Tidak ada; kontak hanya lewat tautan `wa.me`.
- **Basis Data:** Tidak ada; data menu di `data/menu.json`.

### Infrastruktur

- **Hosting:** Cloudflare Pages / Netlify / Vercel (gratis, HTTPS otomatis).
- **Skalabilitas:** CDN bawaan hosting.
- **CI/CD:** Deploy otomatis dari GitHub setiap push ke `main`.

### Struktur Proyek (acuan untuk AI Agent)

```
/index.html
/assets/css, /assets/js/main.js, /assets/images/ (WebP, ≤150KB)
/data/menu.json
/DESIGN.md (referensi desain, letakkan di root proyek)
```

Aturan: satu halaman dengan 6 section ber-ID (`#beranda`, `#fasilitas`, `#menu`, `#lokasi`, `#galeri`, `#kontak`); gunakan konten placeholder yang realistis dan mudah diganti; kode bersih dan dikomentari seperlunya.

## Konten Contoh (Placeholder)

- **Nama/Tagline:** [Nama Cafe]
- **Fasilitas:** Wi-Fi cepat, AC, banyak colokan, area outdoor, parkir luas, musala.
- **Menu (contoh, Rp):**
  - Kopi: Espresso 18.000; Americano 20.000; Kopi Susu Gula Aren 24.000; Cappuccino 26.000
  - Non-Kopi: Matcha Latte 27.000; Coklat Panas 25.000; Teh Lemon 18.000
  - Makanan: Nasi Ayam Sambal Matah 32.000; Mie Goreng Spesial 28.000
  - Camilan: Kentang Goreng 20.000; Roti Bakar Coklat Keju 22.000
- **Lokasi:** [Alamat Cafe]; Senin–Minggu 07.00–22.00.
- **Kontak:** WhatsApp 62812XXXXXXXX (format `wa.me`); Instagram [Nama Instagram].
- **Galeri:** 8–12 foto placeholder (interior, minuman, detail meja, area outdoor; tanpa foto orang sesuai DESIGN.md).

## Analitik & Pemantauan

- **Metrik Utama:** Pengunjung, durasi sesi, klik CTA.
- **Event:** Klik "Petunjuk Arah", klik WhatsApp, buka lightbox, ganti kategori menu.
- **Dashboard:** Google Analytics 4 atau Plausible/Cloudflare Web Analytics.
- **Notifikasi/Alert:** Uptime monitor gratis (mis. UptimeRobot); alert bila situs tidak dapat diakses.

## Perencanaan Rilis

### MVP (v1.0)

- **Fitur:** Navigasi, Beranda, Fasilitas, Menu, Lokasi, Galeri, Kontak, Footer, SEO dasar.
- **Linimasa:** ±1–2 minggu (vibe coding + penyesuaian konten).
- **Kriteria Keberhasilan:** Semua bagian tampil benar di mobile & desktop; Lighthouse ≥ 90; tautan dan peta berfungsi.

### Rilis Mendatang

- **v1.1:** Toggle bahasa ID/EN, mode gelap, integrasi feed Instagram.
- **v1.2:** Halaman event/promo, testimoni pelanggan.
- **v2.0:** Pemesanan/reservasi online, CMS ringan untuk mengubah menu.

## Pertanyaan Terbuka & Asumsi

- **Pertanyaan 1:** Perlu domain khusus (mis. namaCafe.com)? Sudah punya?
- **Pertanyaan 2:** Konten asli (nama, logo, foto, menu, alamat, nomor WhatsApp) menyusul; ganti konten contoh saat sudah siap.
- **Asumsi 1:** Website berupa satu halaman (single page) dengan 6 section dan navigasi anchor, bukan 6 file HTML terpisah.
- **Asumsi 2:** Situs statis tanpa backend; menu dikelola lewat `menu.json`.
- **Asumsi 3:** Hanya bahasa Indonesia untuk v1.
- **Asumsi 4:** Kontak hanya lewat tombol WhatsApp, tanpa formulir.
- **Asumsi 5:** Konten contoh (lihat bagian berikut) dipakai sampai konten asli tersedia.
- **Asumsi 6:** Desain visual mengikuti `DESIGN.md`; font berbayar diganti padanan gratis; kontras warna disesuaikan demi aksesibilitas (lihat Sistem Desain).

## Lampiran

### Glosarium

- **Landing page:** Halaman web tunggal yang berfokus memperkenalkan bisnis dan mendorong aksi.
- **CTA:** Call to Action, tombol/ajakan bertindak.
- **LCP:** Largest Contentful Paint, metrik kecepatan tampil konten utama.
- **Lightbox:** Tampilan foto diperbesar di atas halaman.

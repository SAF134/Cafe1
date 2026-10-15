# AGENTS.md

Website landing page coffee shop (satu halaman, statis, bahasa Indonesia).

## Sumber Kebenaran (baca sebelum coding)

1. `PRD.md`: fitur, kriteria penerimaan, batasan, konten contoh.
2. `DESIGN.md`: token dan aturan visual. Jika PRD dan DESIGN.md bentrok, **PRD menang** (terutama soal kontras/aksesibilitas).
   Jika ada yang ambigu atau tidak tercakup, tanyakan; jangan berasumsi.

## Stack

- HTML5, Tailwind CSS v4 (token dari `DESIGN.md` → `@theme`), JavaScript vanilla (ES6). Build: Vite.
- Tanpa framework (React/Vue), tanpa backend, tanpa database.
- Data menu di `data/menu.json`. Kontak hanya tautan `wa.me`.

## Perintah

- `npm install` · `npm run dev` · `npm run build` · `npm run preview`

## Struktur

```
index.html            # 6 section: #beranda #fasilitas #menu #lokasi #galeri #kontak
src/main.js           # nav, filter menu, lightbox, marquee
src/styles.css        # @theme token + gaya kustom
public/images/           # gambar WebP ≤150KB
data/menu.json
```

## Aturan Wajib

- Satu halaman; navigasi anchor dengan smooth scroll.
- Mobile-first; uji di 360px, 768px, 1280px.
- HTML semantik, `alt` di semua gambar, navigasi keyboard, fokus terlihat, hormati `prefers-reduced-motion`.
- Gunakan token CSS (`var(--color-*)`); **jangan hardcode warna/ukuran** di luar token.
- Teks bermakna pakai Onyx `#2c2c2c` di atas parchment; Walnut/Espresso hanya dekoratif/besar.
- Tombol hanya ghost outlined/teks; kartu radius 0; tanpa shadow; tanpa gradient CSS (kecuali overlay foto).
- Gambar: WebP, `loading="lazy"` (kecuali hero), atribut `width`/`height`.
- Konten placeholder realistis dan terpusat (menu di JSON, teks lain mudah diganti); tandai dengan komentar `<!-- GANTI: ... -->`.
- Teks UI semuanya bahasa Indonesia; kode dan komentar boleh bahasa Inggris.

## Jangan

- Menambah fitur, halaman, atau dependensi di luar PRD tanpa persetujuan.
- Menambah formulir, backend, atau tracking selain yang ada di PRD.
- Memakai foto orang, font tambahan, atau warna aksen kedua.
- Membuat dokumen markdown baru yang tidak diminta.

## Cara Kerja

- Kerjakan per section sesuai urutan PRD; commit kecil dengan pesan jelas (`feat: ...`, `fix: ...`).
- Setelah tiap section: cek tampilan mobile & desktop, tanpa error console.

## Definisi Selesai

- Semua kriteria penerimaan fitur "Must" di `PRD.md` terpenuhi.
- Lighthouse mobile ≥ 90 (Performance, Accessibility, SEO); `npm run build` berhasil.
- Tautan WhatsApp, peta, dan lightbox berfungsi; tidak ada horizontal scroll di mobile.

# 🗣️ Papan Bicara

**Papan Bicara** adalah papan komunikasi bergambar (*picture communication board*) berbasis browser yang dirancang sebagai alat bantu AAC (*Augmentative and Alternative Communication*) sederhana dan gratis. Dapat digunakan oleh penyandang autisme nonverbal, pasien pascastroke, atau siapa pun yang kesulitan berkomunikasi lisan.

> ⚠️ **Disclaimer:** Alat bantu sederhana, bukan pengganti terapis wicara atau perangkat AAC profesional.

---

## Fitur Utama

| Fitur | Keterangan |
|---|---|
| **Kartu bergambar** | Emoji + label teks, dikelompokkan dalam 4 kategori bawaan |
| **Strip kalimat** | Kalimat terbentuk saat kartu diketuk; tampil besar sebagai cadangan visual |
| **Text-to-speech** | Menggunakan Web Speech API; memilih suara `id-ID` secara otomatis |
| **Pilihan suara** | Dropdown di header untuk memilih suara TTS yang tersedia di perangkat |
| **Mode Edit** | Tambah/hapus kartu sendiri; konfirmasi sebelum menghapus |
| **Upload foto** | Foto diperkecil otomatis ke 200 × 200 px dan disimpan lokal |
| **localStorage** | Kartu buatan pengguna tetap tersimpan meski browser ditutup |
| **Offline** | Tidak memerlukan koneksi internet setelah file dibuka |
| **Aksesibel** | `aria-label`, peran keyboard, `aria-live` untuk strip kalimat |
| **Responsif** | Berjalan dari 360 px (ponsel) hingga tablet/desktop |

---

## Cara Pakai

### Penggunaan dasar
1. Buka `index.html` di browser (Chrome, Edge, atau Firefox modern).
2. **Ketuk / klik kartu** untuk menambah kata ke strip kalimat dan mendengar bacaannya.
3. Tekan **🔊 Bacakan** untuk membaca ulang seluruh kalimat.
4. Tekan **⌫ Hapus Terakhir** untuk membatalkan kata terakhir.
5. Tekan **🗑️ Hapus Semua** untuk mengosongkan strip.

### Memilih suara
- Gunakan dropdown **Suara** di header untuk memilih suara `id-ID` (Indonesia) atau suara lain yang tersedia di perangkat Anda.
- Jika tidak ada suara yang tersedia, kalimat tetap tampil dalam teks besar sebagai cadangan.

### Mode Edit
1. Tekan tombol **✏️ Edit** di sudut kanan atas header.
2. Tombol **＋ Tambah** muncul di setiap kategori — klik untuk membuka form:
   - **Label** (wajib): teks yang dibacakan.
   - **Kategori**: pilih kategori yang ada atau "Lainnya".
   - **Emoji**: satu karakter emoji opsional.
   - **Foto**: unggah gambar JPG/PNG/WebP (maks 5 MB); otomatis diperkecil ke 200 × 200 px.
3. Tekan **Simpan** — kartu langsung muncul dan tersimpan di `localStorage`.
4. Untuk **menghapus** kartu buatan sendiri, aktifkan Mode Edit, lalu klik tombol **✕** di pojok kanan atas kartu dan konfirmasi.
5. Tekan **✅ Selesai Edit** untuk keluar dari Mode Edit.

> Kartu bawaan (default) tidak dapat dihapus.

### Pintasan keyboard
| Tombol | Aksi |
|---|---|
| `F1` | Bacakan kalimat |
| `Delete` | Hapus kata terakhir |
| `Enter` / `Space` | Aktifkan kartu yang sedang difokus |
| `Escape` | Tutup modal tambah kartu |

---

## Keterbatasan

- **Suara bergantung perangkat.** Web Speech API menggunakan suara yang terpasang di sistem operasi atau browser. Perangkat lama atau browser tertentu mungkin tidak menyediakan suara `id-ID`.
- **Tidak ada sinkronisasi lintas perangkat.** Data tersimpan di `localStorage` lokal; tidak tersinkronisasi antar ponsel/tablet/komputer.
- **Kapasitas localStorage terbatas** (~5 MB). Foto beresolusi tinggi yang banyak dapat memenuhi kuota. Disarankan menggunakan foto yang sudah dikompres.
- **Tidak ada undo multi-langkah.** Kartu yang dihapus di Mode Edit tidak dapat dikembalikan.
- **Tidak ada fitur ekspor/impor** kartu antara perangkat (rencana pengembangan).
- **Tidak menggantikan perangkat AAC profesional** yang dilengkapi simbol standar, pelatihan, dan dukungan terapis.
- **Tidak diuji dengan screen reader** secara menyeluruh; atribut ARIA yang ada mengikuti praktik terbaik standar WCAG 2.1 AA namun belum divalidasi end-to-end.

---

## Rencana Pengembangan

- [ ] **Ekspor / Impor** kartu pengguna ke file JSON agar bisa dipindahkan antar perangkat.
- [ ] **Simbol AAC standar** (mis. ARASAAC, Mulberry Symbols) sebagai alternatif emoji.
- [ ] **Kata sering dipakai** — histori penggunaan dan pin kartu favorit.
- [ ] **Mode Pemindai** (*scanning mode*) untuk pengguna yang hanya bisa menggunakan satu tombol/saklar.
- [ ] **Ukuran kartu dapat diatur** melalui pengaturan aksesibilitas.
- [ ] **Dukungan PWA** (Progressive Web App) agar bisa diinstal di layar utama ponsel.
- [ ] **Multi-bahasa** antarmuka (selain Bahasa Indonesia).
- [ ] **Profil pengguna** — beberapa konfigurasi kartu berbeda untuk pengguna berbeda pada perangkat yang sama.
- [ ] **Validasi & uji screen reader** (NVDA, TalkBack) secara menyeluruh.
- [ ] **Mode prediksi kata** menggunakan frekuensi penggunaan.

---

## Struktur File

```
index.html   ← Aplikasi lengkap (HTML + CSS + JS, satu file, ~700 baris)
README.md    ← Dokumentasi ini
```

---

## Kompatibilitas Browser

| Browser | Dukungan |
|---|---|
| Chrome / Edge ≥ 90 | ✅ Penuh (TTS + FileReader + Canvas) |
| Firefox ≥ 90 | ✅ Penuh |
| Safari ≥ 14.1 (iOS/macOS) | ✅ Penuh |
| Browser lama / tanpa JS | ⚠️ Kartu tampil, TTS tidak tersedia |

---

## Lisensi

Proyek ini dibagikan sebagai alat bantu bebas pakai (*free to use*). Silakan modifikasi dan distribusikan untuk keperluan non-komersial, terutama untuk mendukung aksesibilitas dan inklusi.

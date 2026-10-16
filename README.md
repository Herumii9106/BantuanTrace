# BantuanTrace

Prototype sistem transparansi penyaluran bantuan pendidikan berbasis wallet pada Solana devnet (simulasi).
Proyek praktikum Keamanan Data dan Blockchain (Modul 1).

**Nama:** Helmy Muhammad Zulkarnaen
**NIM:** G.231.24.0014

## Masalah

Penerima bantuan pendidikan hanya bisa percaya pada catatan pengelola. Mereka tidak punya bukti sendiri
bahwa bantuan sudah disalurkan, dan catatan penyaluran dapat diubah sepihak.

## Solusi

Setiap tahap penyaluran (DIAJUKAN, DISETUJUI, DICAIRKAN, DITERIMA / DIBATALKAN) dicatat sebagai
timeline. Yang "dicatat on-chain" (simulasi) hanya bukti: hash dokumen (SHA-256 dengan salt), status,
timestamp, wallet pelaku, dan kode anonim (contoh: BT-001). Setelah penerima mengonfirmasi, penerima
mendapat bukti terima (kode dan QR) yang bisa diverifikasi sendiri.

## Role

1. Penyalur: mencatat dan mengubah status penyaluran
2. Penerima: melihat status dan mengonfirmasi terima
3. Auditor / Publik: memverifikasi catatan tanpa melihat data pribadi

## Fitur (MVP)

1. Connect wallet (simulasi) dan akses berdasarkan role
2. Pencatatan penyaluran dan dokumen dummy
3. Pencatatan hash, status, dan timestamp (simulasi on-chain)
4. Konfirmasi terima dan bukti terima untuk penerima
5. Audit trail (timeline) dan verifikasi hash (Sesuai / Tidak sesuai)

## Batasan

- Solana devnet (simulasi), tanpa dana nyata
- Semua data dummy; tidak ada data pribadi nyata
- Tidak meminta atau menyimpan private key, seed phrase, atau password
- Smart contract belum diimplementasikan pada Modul 1

## Keamanan

- Data pribadi tidak pernah ditampilkan di halaman publik atau ditulis ke blockchain
- Tidak ada secret atau API key di repository
- Validasi input di sisi klien

## Menjalankan secara lokal

```sh
git clone https://github.com/Herumii9106/BantuanTrace.git
cd BantuanTrace
npm install
npm run dev
```

## Teknologi

React, TypeScript, Tailwind CSS, lucide-react. Prototype antarmuka dibuat dengan Lovable.

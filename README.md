# Perisai Hijau Cirebon

Situs pendamping interaktif untuk poster **Manajemen Risiko Debu Batu Bara — Pelabuhan Cirebon 2026**. Memuat simulasi ambang batas operasional, strategi mitigasi, arsitektur risiko (Capacity/Tolerance/Appetite/Limit), kajian risiko kuantitatif dari RCSA 2026, dan kode QR untuk dibagikan.

## Isi proyek

Situs ini adalah **satu file HTML statis** (`index.html`) tanpa dependensi eksternal — semua font (Baloo 2, Work Sans, IBM Plex Mono) dan pustaka pembuat kode QR sudah disisipkan langsung di dalam file (base64 / inline script). Tidak ada proses build, tidak ada `npm install`, tidak ada panggilan ke server luar saat halaman dibuka.

Ini artinya situs bisa langsung di-deploy ke layanan hosting statis apa pun tanpa konfigurasi tambahan.

## Deploy ke Vercel

**Lewat dashboard (tanpa command line):**
1. Push folder ini ke repository GitHub (lihat langkah di bawah).
2. Buka [vercel.com/new](https://vercel.com/new), pilih **Import Git Repository**, arahkan ke repo tersebut.
3. Framework Preset: pilih **Other** — tidak perlu Build Command atau Output Directory (biarkan kosong / default), karena `index.html` sudah siap pakai di root.
4. Klik **Deploy**. Selesai dalam <1 menit.

**Lewat CLI:**
```bash
npm install -g vercel
vercel
```
Jalankan dari dalam folder ini, ikuti prompt-nya, dan terima jawaban default (tidak perlu build command).

## Deploy ke GitHub Pages

1. Push folder ini ke repository GitHub (lihat langkah di bawah).
2. Di repo tersebut: **Settings → Pages**.
3. Pada **Source**, pilih branch `main` dan folder `/ (root)`.
4. Simpan — GitHub akan menerbitkan situsnya di `https://<username>.github.io/<nama-repo>/` dalam beberapa menit.

## Push ke GitHub (langkah awal, sekali saja)

```bash
git init
git add .
git commit -m "Publikasikan situs Perisai Hijau Cirebon"
git branch -M main
git remote add origin https://github.com/<username>/<nama-repo>.git
git push -u origin main
```
Ganti `<username>/<nama-repo>` dengan repo GitHub kamu. Jika repo belum ada, buat dulu lewat [github.com/new](https://github.com/new) (boleh privat atau publik).

## Update setelah deploy

Setiap kali `index.html` diedit lagi:
```bash
git add .
git commit -m "Update konten"
git push
```
Vercel & GitHub Pages otomatis menerbitkan ulang begitu ada push baru ke branch `main`.

## Kode QR

Kode QR di bagian "Bagikan" pada situs otomatis mengarah ke URL tempat halaman itu dibuka (`window.location.href`) — begitu situs sudah live di domain Vercel/GitHub Pages/domain kustom, kode QR akan otomatis menunjuk ke alamat yang benar tanpa perlu diedit manual.

## Sumber materi

- Poster resmi *Manajemen Risiko Debu Batu Bara — Pelabuhan Cirebon 2026*
- Brief konten poster (Word)
- *Materi Presentasi Penanggulangan Debu Batu Bara* — HSSE Cirebon (PPTX)
- *Kajian Risiko Debu Batubara Cirebon 2026* — sheet RCSA (Excel)

# Trade Checklist

App checklist trading: pilih pair (bisa custom pair sendiri), centang rule konfirmasi setup, lihat skor kesiapan, dan simpan ke jurnal riwayat. Data tersimpan di browser (localStorage) — jadi persist per device/browser, tanpa perlu database.

## Menjalankan di lokal

```bash
npm install
npm run dev
```

Buka http://localhost:3000

## Deploy ke Vercel

**Cara paling gampang (tanpa terminal):**
1. Upload folder ini ke sebuah repo GitHub (buat repo baru, push semua file).
2. Buka https://vercel.com/new, login, pilih "Import Project", lalu pilih repo tersebut.
3. Vercel otomatis mendeteksi Next.js — langsung klik **Deploy**.
4. Tunggu ~1 menit, dapat URL live seperti `https://trade-checklist.vercel.app`.

**Via CLI:**
```bash
npm install -g vercel
vercel
```
Ikuti prompt-nya, lalu `vercel --prod` untuk deploy production.

## Cara pakai

- **Sidebar kiri**: daftar pair. Ketik pair custom (contoh `USDCHF`, `SOLUSDT`) di kolom bawah lalu klik **Add**.
- **Checklist**: centang rule yang sudah terpenuhi. Klik **Kelola rule** untuk menambah/menghapus rule sesuai strategi kamu.
- **Setup Score**: otomatis menghitung persentase rule yang terpenuhi (hijau = siap, kuning = hati-hati, merah = belum siap).
- **Simpan ke jurnal**: menyimpan hasil checklist (pair, bias Buy/Sell, skor, catatan) ke tab Jurnal sebagai riwayat.

## Kustomisasi rule

Rule default sudah diisi contoh generik. Kirim rule trading kamu (misalnya syarat entry, filter tren, aturan risk management), lalu ganti isi `DEFAULT_RULES` di `lib/storage.ts`, atau tambahkan langsung lewat tombol **Kelola rule** di aplikasi — keduanya tersimpan otomatis.

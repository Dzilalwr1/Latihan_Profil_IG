## **Penjelasan Desain**
Desain halaman ini meniru layout profil Instagram dengan pendekatan mobile-first menggunakan Tailwind CSS.

- Header dibuat dengan flex justify-between agar username di kiri dan icon di kanan seimbang.
- Profile info menampilkan foto profil, jumlah posting/followers/following, serta tombol aksi, disusun menggunakan kombinasi flex dan justify-around.
- Bio sederhana hanya teks, dibuat konsisten dengan warna abu-abu untuk deskripsi.
- Story highlights menggunakan flex gap-4 agar icon story tersusun horizontal dan responsif.
- Tabs memakai flex justify-around untuk membagi rata menu grid, reels, dan tagged..Feed memanfaatkan grid dengan breakpoint (`grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4`) sehingga jumlah kolom menyesuaikan lebar layar.
- Bottom navbar hanya tampil di mobile dengan md:hidden agar navigasi tetap mudah di layar kecil.
---

## **PERTANYAAN**
1. Jelaskan keputusan grid-cols/gap di tiap breakpoint — kenapa begitu?
Pada bagian Feed, saya menggunakan kombinasi grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-[2px].
    - grid-cols-1 dipakai default agar di layar kecil (mobile) setiap foto tampil satu kolom penuh → lebih enak di-scroll.
    - `sm:grid-cols-2` supaya di tablet kecil (≥640px) sudah mulai terlihat 2 kolom → memanfaatkan ruang.
    - `md:grid-cols-3` untuk layar sedang (≥768px) menampilkan 3 kolom seperti layout Instagram asli.
    - `lg:grid-cols-4` di layar besar (≥1024px) agar tampilan makin padat, sesuai monitor desktop.
    - `gap-[2px]` dipilih kecil agar antar gambar tidak terlalu renggang, meniru style feed Instagram.

2. Bagaimana kamu memanfaatkan utility responsive Tailwind untuk memecah masalah layout di mobile?
Saya memakai modifier responsive seperti `md:hidden` pada bottom navbar, supaya navigasi hanya muncul di mobile dan hilang di layar besar. Selain itu, flex, grid, dan object-cover dipadukan dengan class responsive (`sm:, md:, lg:`) agar layout otomatis menyesuaikan ukuran layar tanpa harus menulis media query manual.

3. Jelaskan trade-off antara memakai banyak utility classes vs membuat component CSS tersendiri.
    - Utility Classes (Tailwind)
      ✅ Kelebihan: cepat, konsisten, langsung kelihatan hasilnya di HTML.
      ❌ Kekurangan: class bisa panjang & HTML terlihat “berisik”.
    - Component CSS tersendiri
      ✅ Kelebihan: lebih rapi, HTML bersih, class bisa dipakai ulang.
      ❌ Kekurangan: butuh waktu ekstra bikin style sendiri, kadang mengurangi fleksibilitas utility-first.
Jadi trade-off utamanya ada di kecepatan vs kerapian kode. Kalau proyek kecil lebih enak pakai utility langsung, tapi untuk proyek besar bisa dipadukan dengan component agar maintainable.

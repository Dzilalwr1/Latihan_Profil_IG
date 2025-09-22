## **Struktur File:**
    PROFIL IG BOOSTRAP/
    │
    ├── profil_ig.html              # Halaman utama profil Instagram (versi Bootstrap)
    ├── assets/
    │   ├── img/                    # Berisi gambar profil, story, dan feed
    │   └── style.css               # External css untuk profil_ig.html
---

## **Build / Run:**
    1. Pastikan semua file sudah ada di folder boost/.
    2. Simpan gambar profil, story, dan feed di assets/img/.
    3. Buka file index.html langsung di browser (tidak butuh server tambahan).
    4. Semua library (Bootstrap + Icons) sudah dihubungkan via CDN, jadi tidak perlu instalasi manual.
---

## **Dependensi:**
    Bootstrap 5.3.3 (via CDN)
    Bootstrap Icons (via CDN)
---

## **PERTANYAAN:**
    1. Mengapa memilih konfigurasi col tertentu untuk tiap breakpoint?
    Agar layout foto tetap rapi dan responsif sesuai ukuran layar.
    Mobile (≤576px) → 1 kolom supaya feed jelas.
    Tablet (≥768px) → 2–3 kolom agar efisien.
    Desktop (≥992px) → 4 kolom agar mirip Instagram asli.


    2. Bagaimana memastikan tombol Follow/Edit Profile tetap mudah dijangkau di mobile?
    Dengan menggunakan Bootstrap responsive utility class (d-flex, w-100, btn-sm).
    Sehingga tombol otomatis menyesuaikan ukuran layar dan tetap tersusun rapi.

    3. Jika postingan bertambah jadi 50, apa potensi masalah dan bagaimana solusinya?
    Masalah: loading halaman lebih berat, scroll panjang, grid penuh.
    Solusi:
    Gunakan pagination atau lazy loading gambar.
    Atur grid lebih detail dengan breakpoints tambahan agar rapi.

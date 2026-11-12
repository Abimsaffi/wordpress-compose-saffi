# Penugasan Docker Compose: WordPress & MariaDB (Opsi 1)

## Identitas
- **Nama Lengkap:** Muhammad Saffi Abimanyu
- **Kelas:** XI SIJA 1
- **Nomor Absen:** 21
- **Tanggal Pengumpulan:** 11 November 2026

## Deskripsi Project
Project ini dikerjakan menggunakan Opsi 1 (Bikin Sendiri) dengan menyusun `compose.yaml` dari awal untuk menjalankan WordPress dan MariaDB menggunakan Docker Compose.

## Cara Menjalankan
1. `cp .env.example .env`
2. `docker compose config`
3. `docker compose up -d`

## Jawaban Penugasan Eksplorasi
1. **Tujuan Docker Compose & Pemisahan DB:** Mempermudah kelola multi-container. Database dipisah agar data aman dan fleksibel saat update.
2. **Fungsi Service:** `db` sebagai penyimpan data MariaDB, `wordpress` sebagai web server dan mesin PHP.
3. **Parameter:** `image` (versi image), `container_name` (nama container), `restart` (kebijakan restart), `ports` (binding port), `environment` (variabel env), `depends_on` (urutan start), `volumes` (penyimpanan permanen).
4. **WORDPRESS_DB_HOST:** Menggunakan `db:3306` karena memakai DNS internal Docker Compose.
5. **.env vs .env.example vs .gitignore:** `.env` berisi rahasia asli, `.env.example` templat variabel, `.gitignore` menyembunyikan `.env` dari Git.
6. **Persistence Test:** Membuktikan data artikel tidak hilang saat container dimatikan dengan `docker compose down`.
7. **Troubleshooting:** Koneksi DB error saat awal start diatasi dengan `docker compose restart wordpress`.
8. **Modifikasi:** Mengubah port akses WordPress ke `8080:80` dan memakai MariaDB versi 11.

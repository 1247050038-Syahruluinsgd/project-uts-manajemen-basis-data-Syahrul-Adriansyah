# Proyek UTS Manajemen Basis Data

**Mata kuliah:** Manajemen Basis Data  
**Proyek:** PostgreSQL dan pgAdmin menggunakan Docker  
**Database:** `uts_syahrul`  
**Schema:** `SALAM`

## Deskripsi

Proyek ini menjalankan PostgreSQL dan pgAdmin melalui Docker Compose, membuat schema `SALAM` beserta tabel `mahasiswas`, menerapkan constraint, dan menguji hak akses tiga role database.

## Struktur folder

```text
.
├── docker-compose.yml
├── .env.example
├── README.md
├── sql/
│   ├── 01_create_schema_table.sql
│   ├── 02_insert_data.sql
│   └── 03_create_roles_grants.sql
└── laporan/
    ├── laporan_uts.pdf
    └── screenshots/
```

Sesuaikan struktur di atas dengan file yang benar-benar tersedia pada folder proyek.

## Script SQL

1. `sql/01_create_schema_table.sql` membuat schema `SALAM` dan tabel `mahasiswas` dengan primary key, unique constraint, serta check constraint.
2. `sql/02_insert_data.sql` memasukkan data mahasiswa dan menampilkan data untuk verifikasi.
3. `sql/03_create_roles_grants.sql` membuat role jika belum tersedia dan memberikan hak akses sesuai kebutuhan proyek.

Jalankan script melalui Query Tool di pgAdmin pada database `uts_syahrul` menggunakan role administrator yang sesuai.

## Role database

- `backend_dev`: SELECT, INSERT, UPDATE, DELETE pada tabel di schema `SALAM`.
- `bi_dev`: SELECT pada tabel di schema `SALAM`.
- `data_engineer`: CRUD pada tabel dan CREATE pada schema `SALAM`; ALTER/DROP berlaku untuk objek yang dimilikinya.

## Konfigurasi dan keamanan

- File `.env` berisi konfigurasi lokal dan rahasia. **Jangan unggah `.env` asli ke repositori.**
- Gunakan `.env.example` yang tidak berisi password asli sebagai contoh variabel konfigurasi.
- Jangan menuliskan password database asli di README, screenshot publik, atau script yang diunggah.
- Sesuaikan nilai port, nama kontainer, dan variabel dengan `docker-compose.yml` yang sebenarnya.

## Pengujian yang didokumentasikan

- Status kontainer PostgreSQL dan pgAdmin.
- Koneksi PostgreSQL dari pgAdmin dan DBeaver.
- Keberadaan schema dan tabel.
- Pengujian primary key, unique, dan check constraint.
- Pengujian hak akses `backend_dev`, `bi_dev`, dan `data_engineer`.

## Catatan

Script ini merupakan dokumentasi yang dapat dijalankan. Periksa struktur tabel dan constraint yang benar-benar digunakan pada database sebelum menjalankan script pertama kali pada database yang berisi data.

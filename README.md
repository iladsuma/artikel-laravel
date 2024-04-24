# Instalasi

1. Clone repositori ini & perbarui dependensi menggunakan composer.

```sh
$ cd laravelblog
$ composer update
```

2. Pasang dependensi NPM:

```sh
$ npm install
```

3. Bangun Vite menggunakan NPM:

```sh
$ npm run build
```

4. Salin berkas .env.example.

```sh
$ cp .env.example .env
```

5. Buat database MySQL baru dan atur database baru di berkas .env.

```sh
DB_DATABASE=nama_database
DB_USERNAME=root
DB_PASSWORD=
```

6. Buka berkas seeder yang terletak di `database/seeders/AdminSeeder.php` untuk kredensial login admin.

```php
$name = 'admin'; // nama pengguna
DB::table('users')->insert([
  'name' => $name,
  'slug' => Str::slug($name),
  'email' => 'admin@edu.com', // surel
  'role' => 'admin', // peran
  'password' => Hash::make("12345678") // kata sandi
]);
```

7. Buat kunci aplikasi:

```sh
$ php artisan key:generate
```

8. Jalankan migrasi & seeder:

```sh
$ php artisan migrate --seed
```

9. Jalankan proyek:

```sh
$ php artisan serve
```

# Fitur
vite, mysql, laravel
- Halaman Depan
  - Masuk & daftar.
  - Cari artikel.
  - Tambahkan komentar pada artikel.
  - Filter artikel berdasarkan kategori, tag, atau pengguna.
- Dasbor
  - Peran [Admin/Penulis].
  - CRUD artikel.
  - Manajemen komentar.
  - Buat & hapus kategori. (Hanya Admin)
  - Manajemen pengguna. (Hanya Admin)
  - Riwayat masuk. (Hanya Admin)
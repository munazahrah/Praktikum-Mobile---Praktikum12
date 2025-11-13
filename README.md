# Praktikum 12

Project Modul 12 - Akses Lokasi dengan GPS

📖 Deskripsi

Project ini berfokus pada integrasi dengan fitur perangkat keras (hardware) ponsel, yaitu GPS. Anda akan belajar cara mengambil data lokasi real-time dari perangkat pengguna.

Fokus utamanya adalah mengimplementasikan package geolocator untuk mendapatkan koordinat (Latitude & Longitude) dan package geocoding untuk mengubah koordinat tersebut menjadi alamat yang dapat dibaca manusia (Reverse Geocoding). Modul ini juga sangat menekankan pada penanganan izin (permission) di Android.

🎯 Tujuan Utama Project

Mengakses GPS: Mampu mengambil data lokasi (Latitude & Longitude) perangkat secara real-time menggunakan package geolocator.

Penanganan Izin (Permission): Mengelola alur permintaan izin lokasi kepada pengguna di Android (ACCESS_FINE_LOCATION).

Reverse Geocoding: Mampu mengubah data koordinat yang didapat menjadi data alamat (seperti kelurahan, kecamatan, kota) menggunakan package geocoding.

Manajemen State: Menggunakan StatefulWidget dan setState() untuk memperbarui UI secara dinamis dengan informasi lokasi yang telah didapat.

Penanganan Error: Menangani berbagai skenario kegagalan, seperti jika GPS mati atau jika pengguna menolak izin.

✅ Daftar Tugas (To-Do List)

Berikut adalah hal-hal yang harus Anda kerjakan untuk membuat aplikasi pelacak lokasi:

Buat Project Baru:

[ ] Buat "New Flutter Project" (misal: gps_location_app).

Konfigurasi Izin Android (Penting!):

[ ] Buka file android/app/src/main/AndroidManifest.xml.

[ ] Tambahkan izin berikut di atas tag <application>:

<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />


Tambahkan Dependency:

[ ] Buka file pubspec.yaml.

[ ] Tambahkan package geolocator dan geocoding.

[ ] Jalankan flutter pub get di terminal.

Buat StatefulWidget:

[ ] Buat StatefulWidget untuk halaman utama Anda.

[ ] Definisikan variabel state untuk menampung data lokasi:

String locationMessage = "Lokasi Belum Diambil";

String address = "";

Buat Tampilan UI:

[ ] Buat Scaffold dengan AppBar (judul: "Aplikasi GPS").

[ ] Di body, tampilkan isi variabel locationMessage dan address di dalam Text atau Card.

[ ] Tambahkan ElevatedButton dengan teks "Dapatkan Lokasi".

Implementasi Fungsi getLocation():

[ ] Buat fungsi async void getLocation() (atau nama serupa).

[ ] Cek Layanan: Periksa jika layanan lokasi aktif (await Geolocator.isLocationServiceEnabled()).

[ ] Cek Izin: Periksa status izin (await Geolocator.checkPermission()).

[ ] Minta Izin: Jika izin ditolak, minta izin (await Geolocator.requestPermission()). Tangani kasus denied dan deniedForever.

[ ] Ambil Posisi: Jika izin diberikan, ambil posisi saat ini (await Geolocator.getCurrentPosition()).

[ ] Reverse Geocoding: Gunakan placemarkFromCoordinates() dari package geocoding untuk mengubah latitude dan longitude menjadi alamat.

[ ] Panggil setState(): Perbarui variabel state (locationMessage dan address) dengan data baru yang didapat.

[ ] Gunakan try-catch untuk menangani error.

Hubungkan UI dengan Logic:

[ ] Atur onPressed pada ElevatedButton Anda untuk memanggil fungsi getLocation().

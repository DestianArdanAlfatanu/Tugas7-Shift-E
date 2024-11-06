# Cara Kerja Login

1. Pengguna Mengisi Form Login
- Pengguna memasukkan username dan password pada form login, lalu menekan tombol Login.
2. Validasi Login (postMethod)
- Aplikasi mengirim data login (username dan password) ke server menggunakan postMethod.
- Server memeriksa kredensial yang diberikan dan mengembalikan status login serta token autentikasi jika login berhasil.
3. Penyimpanan Data Login
- Jika login berhasil, token dan username disimpan dalam penyimpanan lokal menggunakan Capacitor Preferences.
- Status isAuthenticated diubah menjadi true, menandakan bahwa pengguna telah berhasil diautentikasi.
4. Navigasi ke Halaman Utama
- Setelah login berhasil, pengguna secara otomatis diarahkan ke halaman home.
5. Pengguna yang Belum Login
- Jika pengguna mencoba mengakses halaman yang membutuhkan autentikasi (misalnya halaman home) tanpa login, authGuard akan mencegah akses dan mengarahkan mereka kembali ke halaman login.
6. Logout
- Saat pengguna memilih untuk logout, AuthenticationService menghapus data login (token dan username) dari penyimpanan lokal.
- Status isAuthenticated diubah kembali menjadi false, dan pengguna diarahkan ke halaman login.
7. AutoLogin
- Jika pengguna telah login sebelumnya, autoLoginGuard akan memeriksa status login mereka saat aplikasi dibuka kembali.
- Jika masih valid, pengguna akan langsung diarahkan ke halaman utama tanpa perlu login ulang.

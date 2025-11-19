# Tugas 7
## 1. Jelaskan apa itu widget tree pada Flutter dan bagaimana hubungan parent-child (induk-anak) bekerja antar widget.
Widget tree pada Flutter adalah struktur hierarkis dari semua widget yang digunakan dalam aplikasi Flutter yang menggambarkan antarmuka pengguna (UI) sebuah aplikasi, dimana setiap widget dapat memiliki child/children.
Parent widget adalah widget yang membungkus atau menaungi widget lain, sedangkan child widget adalah widget yang ditempatkan di dalam parent widget.
Hubungan parent-child menentukan tata letak dan fungsionalitas, dimana parent widget mengontrol bagaimana child widget-nya ditampilkan dan bagaimana child widget memengaruhi parent widgetnya.

## 2. Sebutkan semua widget yang kamu gunakan dalam proyek ini dan jelaskan fungsinya.
- MaterialApp: widget utama (root) yang menyediakan tema dan konfigurasi aplikasi.
- Scaffold: menyediakan struktur dasar halaman seperti AppBar dan body.
- AppBar: menampilkan bar di bagian atas aplikasi dengan judul.
- Text: menampilkan teks pada layar.
- Padding: memberikan jarak di sekitar widget lain.
- Column: menyusun widget secara vertikal.
- Row: menyusun widget secara horizontal.
- Card: menampilkan kotak dengan efek bayangan.
- Container: mengatur ukuran, padding, dan warna dari sebuah area.
- GridView.count: menyusun item dalam bentuk grid dengan jumlah kolom tertentu.
- Icon: menampilkan ikon dari Flutter Icons.
- Material: memberikan efek visual material design pada widget.
- InkWell: menangani event tap dengan efek ripple.
- SnackBar: menampilkan pesan sementara di bagian bawah layar.

## 3. Apa fungsi dari widget MaterialApp? Jelaskan mengapa widget ini sering digunakan sebagai widget root.
Widget MaterialApp adalah widget root yang menyediakan konfigurasi utama aplikasi seperti tema, navigasi, title aplikasi, debug banner, dan lain-lain.
Widget MaterialApp sering menjadi widget root karena merupakan titik awal untuk mengelola seluruh antarmuka dan fungsionalitas aplikasi, serta diperlukan agar widget lain seperti Scaffold dan AppBar dapat berfungsi dengan benar dan mewarisi data tema.

## 4. Jelaskan perbedaan antara StatelessWidget dan StatefulWidget. Kapan kamu memilih salah satunya?
StatelessWidget bersifat statis dan tidak berubah setelah dibuat, sedangkan StatefulWidget bersifat dinamis dan dapat berubah karena interaksi pengguna atau perubahan data.
StatelessWidget digunakan untuk antarmuka yang sederhana dan tidak memerlukan pembaruan data, sedangkan StatefulWidget digunakan untuk komponen yang perlu diperbarui secara dinamis, seperti tombol interaktif, animasi, atau formulir input.

## 5. Apa itu BuildContext dan mengapa penting di Flutter? Bagaimana penggunaannya di metode build?
BuildContext adalah objek yang merepresentasikan posisi widget di dalam widget tree. Ini penting karena menyediakan konteks runtime untuk mengakses informasi penting seperti tema, lokalisasi, atau bahkan untuk menemukan State dari widget ancestor.
Di dalam metode build, BuildContext digunakan untuk mengkonfigurasi dan membangun widget lainnya, misalnya untuk menavigasi, menampilkan dialog, atau mendapatkan data dari widget lain dalam widget tree.

## 6. Jelaskan konsep "hot reload" di Flutter dan bagaimana bedanya dengan "hot restart".
Hot Reload digunakan untuk mempercepat pengembangan karena perubahan UI langsung terlihat tanpa harus menjalankan ulang aplikasi sepenuhnya. Cara kerjanya yaitu dengan menyuntikkan berkas kode yang telah diedit langsung ke dalam mesin virtual (VM) Dart saat aplikasi berjalan. VM akan memperbarui kelas dengan versi baru, lalu framework Flutter akan membangun ulang pohon widget.
Bedanya hot reload dengan hot restart adalah hot reload mempertahankan state dengan memperbarui kode dan langsung menerapkan perubahan ke aplikasi tanpa menghapus state yang sedang berjalan, sedangkan hot restart memulai ulang seluruh aplikasi dari awal, memuat ulang semua state dan variabel.

# Tugas 8
## 1. Jelaskan perbedaan antara Navigator.push() dan Navigator.pushReplacement() pada Flutter. Dalam kasus apa sebaiknya masing-masing digunakan pada aplikasi Football Shop kamu?
Navigator.push() digunakan untuk menambahkan halaman baru di atas halaman sebelumnya di stack navigasi sehingga user bisa kembali ke halaman sebelumnya dengan tombol 'back', sedangkan
Navigator.pushReplacement() digunakan untuk mengganti halaman saat ini dengan halaman baru tanpa menyimpannya di stack sehingga user tidak dapat kembali ke halaman sebelumnya dengan tombol 'back'.
Pada aplikasi saya, pada bagian Add Product di product_card.dart menggunakan Navigator.push() agar user bisa mengisi form, lalu nanti bisa menekan tombol 'back' untuk kembali ke halaman utama.
Lalu pada bagian Drawer di left_drawer.dart menggunakan Navigator.pushReplacement() agar kalau sudah memilih menu baru, halaman sebelumnya tidak perlu disimpan ke stack.

## 2. Bagaimana kamu memanfaatkan hierarchy widget seperti Scaffold, AppBar, dan Drawer untuk membangun struktur halaman yang konsisten di seluruh aplikasi?
Saya menggunakan struktur widget yang sama di semua halaman agar tampilannya konsisten.
Scaffold sebagai struktur utama tiap halaman (tempat untuk AppBar, Drawer, dan body).
AppBar untuk menampilkan judul halaman di bagian atas.
Drawer berisi navigasi ke halaman lain sehingga user dapat berpindah antarhalaman dengan mudah tanpa perlu kembali ke Home terlebih dahulu.

## 3. Dalam konteks desain antarmuka, apa kelebihan menggunakan layout widget seperti Padding, SingleChildScrollView, dan ListView saat menampilkan elemen-elemen form? Berikan contoh penggunaannya dari aplikasi kamu.
Layout widget tersebut membuat tampilan form menjadi rapi, fleksibel, dan responsif.
Padding berfungsi memberi jarak antarelemen agar tidak menempel satu sama lain. Contohnya di productlist_form.dart saya pakai Padding di setiap TextFormField agar inputnya punya ruang di sekelilingnya.
SingleChildScrollView berfungsi agar form bisa discroll kalau isinya banyak, terutapa di layar kecil. Contohnya di productlist_form.dart seluruh form dibungkus dengan SingleChildScrollView agar semua input bisa diakses tanpa overflow.
ListView berfungsi untuk memungkinkan elemen-elemen panjang bisa discroll secara vertikal. Contohnya di left_drawer.dart saya menggunakan ListView agar item navigasi di Drawer bisa discroll kalau isinya banyak.

## 4. Bagaimana kamu menyesuaikan warna tema agar aplikasi Football Shop memiliki identitas visual yang konsisten dengan brand toko?
Saya menggunakan ThemeData di main.dart untuk membuat warna tema utama aplikasi. Saya menggunakan warna biru sebagai warna utama di AppBar, tombol, dan Drawer agar identik dengan nuansa olahraga. Dengan tema ini, seluruh halaman punya identitas visual yang konsisten dan mudah dikenali sebagai warna khas "Football Shop".

# Tugas 9
## 1. Jelaskan mengapa kita perlu membuat model Dart saat mengambil/mengirim data JSON? Apa konsekuensinya jika langsung memetakan Map<String, dynamic> tanpa model (terkait validasi tipe, null-safety, maintainability)?
Kita perlu membuat model Dart saat mengambil/mengirim data JSON untuk keamanan tipe data (type-safety), kemudahan pengelolaan, skalabilitas aplikasi, IDE support, mencegah typo, dan JSON parsing tetap konsisten.
Jika langsung memetakan Map<String, dynamic> tanpa model, konsekuensinya adalah:
1) Terkait validasi tipe
- Kita tidak akan tahu tipe data suatu variabel (misal kita tidak tahu apakah price itu String, int, atau double)
- Raw Map bisa berisi tipe salah maka akan crash runtime
2) Terkait null-safety
- Jika null, bisa crash misal product["thumbnail"] dapat menyebabkan crash jika null tetapi jika menggunakan thumbnail ?? "" akan aman
3) Terkait maintainability
- Pada Raw Map, jika API berubah, harus mengubah banyak file, sedangkan dengan model cukup update class model saja

## 2. Apa fungsi package http dan CookieRequest dalam tugas ini? Jelaskan perbedaan peran http vs CookieRequest.
Dalam tugas ini, package http berfungsi untuk melakukan perintah HTTP request yang digunakan dalam penerapan fetch data dari Django untuk ditampilkan ke Flutter, sedangkan CookieRequest digunakan dalam integrasi sistem autentikasi pada Flutter.
Package http digunakan untuk:
- Request sederhana (GET/POST) tanpa autentikasi login Django
- Tidak menyimpan cookie
- Tidak bisa otomatis mengirim sessionid
CookieRequest digunakan untuk:
- Menyimpan cookie session di Django (sessionid)
- Manajemen autentikasi otomatis
- CORS dan CSRF friendly
- Digunakan untuk semua request yang perlu login

## 3. Jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.
Instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter karena CookieRequest menyimpan session dan cookie Django.
Jika dibuat instance baru, maka cookie hilang, user dianggap belum login, semua request terproteksi gagal, dan logout/login jadi kacau.
Maka kita memakai Provider<CookieRequest> karena Provider menjamin ada satu instance global CookieRequest, semua halaman bisa pakai request yang sama, dan state login tidak hilang saat berpindah halaman.

## 4. Jelaskan konfigurasi konektivitas yang diperlukan agar Flutter dapat berkomunikasi dengan Django. Mengapa kita perlu menambahkan 10.0.2.2 pada ALLOWED_HOSTS, mengaktifkan CORS dan pengaturan SameSite/cookie, dan menambahkan izin akses internet di Android? Apa yang akan terjadi jika konfigurasi tersebut tidak dilakukan dengan benar?
Agar Flutter bisa terhubung dengan Django, kita harus mengatur beberapa konfigurasi penting.
Pertama, alamat 10.0.2.2 ditambahkan ke ALLOWED_HOSTS karena Android Emulator tidak bisa mengakses localhost secara langsung sehingga Django perlu mengenali 10.0.2.2 sebagai host yang valid.
Kemudian, CORS harus diaktifkan agar Django mengizinkan permintaan dari domain atau perangkat Flutter, karena tanpa ini request akan diblokir oleh kebijakan keamanan lintas-origin.
Selain itu, karena autentikasi menggunakan cookie, kita perlu mengatur SameSite=None dan Secure=True supaya cookie sesi dan CSRF boleh dikirim dari Flutter. Jika tidak, pengguna selalu dianggap belum login.
Terakhir, Flutter harus diberi izin akses internet melalui konfigurasi Android, karena aplikasi Android secara default tidak boleh melakukan request jaringan.
Jika salah satu dari konfigurasi ini tidak dilakukan, Flutter tidak dapat mengambil data, mengirim data, atau melakukan autentikasi ke server Django.

## 5. Jelaskan mekanisme pengiriman data mulai dari input hingga dapat ditampilkan pada Flutter.
Pada aplikasi, proses pengiriman data dimulai ketika pengguna mengisi sebuah formulir di Flutter, misalnya menambahkan produk baru.
Setelah pengguna menekan tombol submit, Flutter mengambil seluruh nilai input dan mengubahnya menjadi bentuk data terstruktur (biasanya Map atau model Dart).
Data ini kemudian dikirim ke server Django melalui permintaan HTTP POST menggunakan CookieRequest apabila endpoint tersebut membutuhkan autentikasi.
Di sisi backend, Django menerima permintaan tersebut, memvalidasi seluruh field, lalu menyimpan data ke database.
Setelah data berhasil ditulis, Django mengembalikan respons JSON yang berisi hasil akhir atau status success.
Flutter menerima JSON tersebut, memetakannya kembali ke model Dart, lalu menampilkan informasi terbaru di layar.
Dengan mekanisme ini, perubahan yang terjadi pada backend dapat langsung tersinkronisasi dan muncul pada tampilan pengguna di Flutter.

## 6. Jelaskan mekanisme autentikasi dari login, register, hingga logout. Mulai dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.
Ketika pengguna melakukan register atau login, Flutter mengirimkan data akun (username, password, dan lainnya) ke endpoint Django melalui CookieRequest.
Kemudian, Django memproses permintaan tersebut menggunakan sistem autentikasi bawaan—memeriksa apakah username valid dan apakah password cocok.
Jika login berhasil, Django membuat session dan mengirimkan cookie sesi kembali ke Flutter. Cookie ini disimpan secara otomatis di dalam CookieRequest.
Selama cookie session masih tersimpan, semua permintaan Flutter berikutnya yang memerlukan autentikasi (misalnya menampilkan produk milik user tertentu atau menambahkan item baru) akan menyertakan cookie tersebut sehingga Django dapat mengenali identitas user.
Ketika user memilih logout, Flutter memanggil endpoint logout Django, Django menghapus session, dan CookieRequest menghapus cookie yang tersimpan. Setelah itu, pengguna dianggap tidak lagi login dan diarahkan kembali ke halaman awal aplikasi.

## 7. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial).
1) Membuat django-app bernama authentication di project Django football-shop.
2) Membuat fungsi login pada authentication/views.py dan lakukan routing.
3) Menginstall package Flutter untuk melakukan kontak dengan web service Django. Lalu, modifikasi root widget untuk menyediakan CookieRequest library ke semua child widgets dengan menggunakan Provider.
4) Membuat file login.dart di folder screens.
5) Membuat fungsi register pada authentication/views.py dan lakukan routing.
6) Membuat file register.dart di folder screens.
7) Membuat model kustom dengan menempel data JSON ke dalam file baru lib/models/product_entry.dart.
8) Menambahkan dependensi HTTP dengan menambah package http dan menambahkan permission di android/app/src/main/AndroidManifest.xml.
9) Menambah endpoint proxy untuk mengatasi masalah CORS pada gambar.
10) Membuat fungsi proxy_image pada main/views.py dan lakukan routing.
11) Membuat file product_entry_card.dart di folder widgets.
12) Membuat file product_entry_list.dart di folder screens.
13) Navigate ke ProductEntryListPage.
14) Membuat file product_detail.dart di folder screens.
15) Navigate ke ProductDetailPage.
16) Membuat fungsi create_product_flutter pada main/views.py dan lakukan routing serta menyambungkannya dengan aplikasi.
17) Membuat fungsi show_json_user pada main/views.py dan memodifikasi product_entry_list untuk menambah fungsi filtering my products.
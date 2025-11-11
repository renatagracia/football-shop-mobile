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
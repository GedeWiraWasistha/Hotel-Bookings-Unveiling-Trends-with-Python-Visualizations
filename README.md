# Investigate-Hotel-Business-Using-Data-Visualization


## Latar Belakang
Sangat penting bagi suatu perusahaan untuk selalu menganalisa performa bisnisnya. Pada kesempatan kali ini, kita akan lebih mendalami bisnis dalam bidang perhotelan. Fokus yang kita tuju adalah untuk mengetahui bagaimana perilaku pelanggan kita dalam melakukan pemesanan hotel, dan hubungannya terhadap tingkat pembatalan pemesanan hotel. Hasil dari insight yang kita temukan akan kita sajikan dalam bentuk data visualisasi agar lebih mudah dipahami dan bersifat lebih persuasif.

## Objective
Membuat visualisasi berbasis analisa data untuk menghasilkan insight yang meaningfull dalam pengambilan keputusan.

## Dataset
Data yang digunakan dalam analisis tersedia dalam berkas "hotel_bookings_data.csv". Yang terdiri dari 119390 baris, 29 kolom

## Data Preprocessing

### Mengatasi Null Value
![1  Mengatasi Null Value](https://github.com/GedeWiraWasistha/Investigate-Hotel-Business-Using-Data-Visualization/assets/149849772/b71ccb4c-c39c-40c4-ac80-85c05bf484d2)

Pada tahapan  mencari nilai null menggunakan df.isnull().sum(), didapatkan hasil 4 kolom yang memiliki nilai null. Kolom children memiliki 4 data null, diatasi dengan mengganti nilai null dengan median. Kolom city memiliki 488 data null, diatasi dengan mengganti nilai null dengan modus. Kolom agent memiliki 16340 data null, diatasi dengan mengganti nilai null dengan modus. Kolom company memiliki 112593 data null. Karena dikhawatirkan akan menimbulkan bias jika nilai null diisi dengan modus ataupun median, maka kolom ini di drop.  

### Mengganti Value Tidak Sesuai
![2  Mengganti Value Tidak Sesuai](https://github.com/GedeWiraWasistha/Investigate-Hotel-Business-Using-Data-Visualization/assets/149849772/69b70629-17b4-42b5-ae89-9125e6c6df85)

![3  Mengganti Value Tidak Sesuai](https://github.com/GedeWiraWasistha/Investigate-Hotel-Business-Using-Data-Visualization/assets/149849772/10097c35-ab95-449e-abed-1bb18418315f)

- Dalam kolom ‘meal’ terdapat  5 nilai unik yaitu 'Breakfast', 'Full Board', 'Dinner', 'No Meal', 'Undefined'.
- 'Breakfast', 'Full Board', 'Dinner', 'No Meal' mewakili paket makanan apa yang dipesan oleh tamu. Sedangkan 'Undefined' tidak mewakili apa-apa. Sehingga saya meengganti nilai 'Undefined' menjadi 'No Meal'

### Membuang Data yang Tidak Diperlukan
![4  Membuang Data yang Tidak Diperlukan](https://github.com/GedeWiraWasistha/Investigate-Hotel-Business-Using-Data-Visualization/assets/149849772/3a865a9c-b080-4c60-8fc9-01112ac9f473)

- Dalam kolom adults, children, & babies terdapat baris yang berisikan 0 pada satu baris. Ini tidak mungkin terjadi karena tidak mungkin jika seseorang memesan kamar hotel namun tidak mencantumkan menginap untuk berapa orang
- Dalam kolom adults juga terdapat keganjilan yaitu terdapat tamu yang mengisi satu kamar 10-55 orang dewasa, satu kamar hotel ditempati oleh 10 orang anak, dan satu kamar hotel ditempati 9-10 bayi. Hal ini tidak masuk akal, karena pada dasarnya hotel hanya mengizinkan satu kamar hotel ditempati maksimal 4-5 orang.

## Monthly Hotel Booking Analysis Based on Hotel Type
![5  Monthly Hotel Booking Analysis Based on Hotel Type](https://github.com/GedeWiraWasistha/Investigate-Hotel-Business-Using-Data-Visualization/assets/149849772/8ea2f1f0-da4c-4e07-a0bc-1238e1a31d48)


Kedua tipe hotel yaitu City Hotel dan Resort Hotel cenderung mengalami peningkatan pada musim liburan, khususnya pada periode Mei - July. 
Pada bulan juni 2017-2019 merupakah hari dimana cuti bersama idul fitri dan pada bulan juni-juli merupakan hari libur semester sekolah/kuliah. Libur Idul Fitri memungkinkan masyarakat untuk berlibur. Selain itu, mayoritas penduduk Indonesia beragama Islam dan  budaya mudik berkumpul saat lebaran memungkinkan masyarakat melakukan perjalanan jauh dan membutuhkan tempat menginap selama bepergian sehingga memesan kamar hotel. <br>
Sementara pada bulan desember terdapat jadwal cuti bersama dimulai dari tanggal 23 sampai awal tahun, pada musim liburan  November hingga Desember, pemesanan hotel juga meningkat namun cenderung lebih rendah dibandingkan musim liburan sebelumnya. Sepertinya banyak orang yang suka merayakan hari raya seperti Natal dan Tahun Baru di rumah. <br>
Bisnis perhotelan merupakan sektor yang beroperasi dalam siklus tahunan yang diselingi oleh season. Secara umum, bulan November hingga Maret merupakan periode low season dimana pengunjung biasanya tidak begitu ramai. Antara bulan Juni dan akhir september adalah high season, dimana banyak tamu yang berkunjung. ini adalah pola yang terjadi dalam bisnis perhotelan dan pariwisata

## Impact Analysis of Stay Duration on Hotel Bookings Cancellation Rates
![6  Impact Analysis of Stay Duration on Hotel Bookings Cancellation Rates](https://github.com/GedeWiraWasistha/Investigate-Hotel-Business-Using-Data-Visualization/assets/149849772/75e83bd2-d796-4308-9db4-b7d0af70a2ca)

Hasil analisis menunjukkan  terdapat hubungan positif antara lama menginap dengan risiko pembatalan, yang berlaku secara konsisten baik pada City Hotel dan Resort Hotel. Dengan kata lain, semakin lama masa tinggal semakin besar kemungkinan pesanan dibatalkan, dan hasil ini tetap konsisten untuk setiap lama tinggal kelompok  yang  dianalisis.
Selain itu, ketika membandingkan City Hotel dan Resort Hotel, ditemukan bahwa City Hotel cenderung memiliki risiko pembatalan yang lebih tinggi dibandingkan Resort Hotel. Tren ini dapat diamati dan diverifikasi di setiap kelompok lama menginap, menunjukkan bahwa beberapa faktor yang mungkin terkait dengan jenis hotel atau lingkungan dapat mempengaruhi tingkat pembatalan.


## Impact Analysis of Lead Time on Hotel Bookings Cancellation Rate
![7  Impact Analysis of Lead Time on Hotel Bookings Cancellation Rate](https://github.com/GedeWiraWasistha/Investigate-Hotel-Business-Using-Data-Visualization/assets/149849772/0b98ab70-b42e-430b-b5a9-2d5b41816747)
  
Pada kedua jenis hotel, tingkat pembatalan pesanan hotel paling rendah adalah pada pesanan yang memiliki Lead Time 1-30 hari. Sedangkan untuk pesanan yang memiliki Lead Time antara 300-420 memiliki tingkat pembatalan tertinggi. Dapat diketahui juga City Hotel memiliki resiko pembatalan lebih besar ketimbang Resort Hotel, hal ini berlaku untuk masing-masing grouping Lead Time




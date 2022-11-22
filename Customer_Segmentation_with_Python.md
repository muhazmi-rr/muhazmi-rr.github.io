# Segmentasi Pelanggan Menggunakan Python
## Deskripsi Proyek
Perusahaan sedang berusaha untuk mengenal lebih baik pelanggannya. Tujuannya agar perusahaan dapat membuat strategi pemasaran yang lebih tepat dan juga efisien bagi tiap tiap pelanggan. Saya diberikan tugas agar dapat memberikan rekomendasi untuk menyelesaikan permasalahan tersebut.
Salah satu teknik yang bisa dilakukan untuk mengenal lebih baik pelanggan adalah dengan melakukan segmentasi pelanggan. Yaitu dengan mengelompokkan pelanggan-pelanggan yang ada berdasarkan kesamaan karakter dari pelanggan tersebut. Saya akan menggunakan algoritma K-Prototypes dalam segmentasi ini.

## Penentuan Banyaknya Cluster
Dalam menentukan banyaknya cluster itu tidak sembarangan. Harus dicari nilai optimalnya dengan melihat kedalam inertia plot. Gambar berikut merupakan inertia plot yang sudah dibuat di proyek ini.  
<img src="Customer Segmentation with Python/1.png?raw=true"/>  
Inertia plot menunjukkan bahwa banyaknya cluster yang terletak pada “elbow” adalah 5 sehingga banyak cluster yang optimal untuk proyek ini adalah 5.

## Pemodelan
Selanjutnya melakukan pemodelan berdasarkan banyak cluster yang sudah ditentukan yakni 5. Hasil pemodelan disimpan dalam variabel bernama “kproto”.  
<img src="Customer Segmentation with Python/2.png?raw=true"/>

## Segmentasi
Model lalu digunakan untuk melakukan segmentasi pada semua pelanggan. Hasil segmentasi disimpan dalam dataframe bernama “df_final”. Untuk pengecekan, 10 data teratas dari hasil segmentasi akan ditampilkan.  
<img src="Customer Segmentation with Python/3.png?raw=true"/>  
<img src="Customer Segmentation with Python/4.png?raw=true"/>  
Nampak kolom cluster yang merupakan hasil dari segmentasi. Kita perlu mengobservasi kolom cluster ini agar dapat insightnya. Observasi dilakukan lewat visualisasi.

## Visualisasi
Agar mengerti apa yang akan kita visualisasikan, mari kita melihat informasi dataset terlebih dahulu.  
<img src="Customer Segmentation with Python/5.png?raw=true"/>  
Setelah melihat daftar kolom beserta keterangan jenis datanya. Saya memutuskan untuk membuat box plot umur, box plot nilai belanja setahun, count plot jenis kelamin, dan count plot profesi agar dapat melihat karakteristiknya di tiap-tiap kategori cluster.
* Box Plot Umur  
  <img src="Customer Segmentation with Python/6.png?raw=true"/>  
  Box plot dari kolom Umur memberikan informasi perihal karakteristik rentang umur di tiap-tiap kategori cluster. Dari box plot ini dapat dipahami bahwa rentang umur anggota-anggota cluster 0 berada di sekitar 14-19 tahun, rentang umur anggota-anggota cluster 1 berada di sekitar 45-64 tahun, rentang umur anggota-anggota cluster 2 berada di sekitar 46-63 tahun, rentang umur anggota-anggota cluster 3 berada di sekitar 18-41 tahun, dan rentang umur anggota-anggota cluster 4 berada di sekitar 20-40 tahun.  
* Box Plot Nilai Belanja Setahun  
  <img src="Customer Segmentation with Python/7.png?raw=true"/>  
  Box plot dari kolom Nilai Belanja Setahun memberikan informasi perihal karakteristik rentang nilai belanja selama setahun di tiap-tiap kategori cluster. Adanya tulisan “1e7” di atas sumbu y bermakna bahwa nilai sebenarnya dari sumbu y adalah di kali 10^7. Dari box plot ini dapat dipahami bahwa nilai belanja setahun dari anggota-anggota cluster 0 berada di sekitaran 3 juta, nilai belanja setahun dari anggota-anggota cluster 1 berada di sekitaran 10 juta, nilai belanja setahun dari anggota-anggota cluster 2 berada di sekitaran 5,5 juta, nilai belanja setahun dari anggota-anggota cluster 3 berada di sekitaran 10 juta, dan nilai belanja setahun dari anggota-anggota cluster 4 berada di sekitaran 5,5 juta.  
* Count Plot Profesi  
  <img src="Customer Segmentation with Python/8.png?raw=true"/>  
  Count plot dari kolom Profesi menunjukkan karakteristik dari jenis profesi anggota-anggota cluster. Dari count plot ini dapat dipahami bahwa anggota-anggota cluster 0 merupakan para pelajar dan mahasiswa, anggota-anggota cluster 1 merupakan para wiraswasta, anggota-anggota cluster 2 merupakan para profesional dan ibu rumah tangga, anggota-anggota cluster 3 merupakan para wiraswasta, dan anggota-anggota cluster 4 merupakan para profesional dan ibu rumah tangga.  
* Count Plot Jenis Kelamin  
  <img src="Customer Segmentation with Python/9.png?raw=true"/>  
  Count plot dari kolom Jenis Kelamin menunjukkan karakteristik dari jenis kelamin anggota-anggota cluster. Dari count plot ini dapat dipahami bahwa anggota-anggota cluster 0 dan 3 semuanya adalah wanita, anggota-anggota cluster 1, 2, dan 4 ada yang pria dan ada yang wanita.
  
## Hasil Observasi
Berdasarkan observasi yang sudah dilakukan pada visualisasi data, saya akan memberikan nama yang menggambarkan masing-masing cluster yakni :
* Cluster 0 saya namakan Silver Young Member. Hal ini karena anggota dari cluster 0 berumur di rentang 14-19 tahun dengan nilai belanja setahunnya di sekitaran 3 juta.
* Cluster 1 saya namakan Diamond Senior Member. Hal ini karena anggota dari cluster 1 berumur di rentang 45-64 tahun dengan nilai belanja setahunnya di sekitaran 10 juta.
* Cluster 2 saya namakan Gold Senior Member. Hal ini karena anggota dari cluster 2 berumur di rentang 46-63 tahun dengan nilai belanja setahunnya di sekitaran 5,5 juta.
* Cluster 3 saya namakan Diamond Adult Member. Hal ini karena anggota dari cluster 3 berumur di rentang 18-41 tahun dengan nilai belanja setahunnya di sekitaran 10 juta.
* Cluster 4 saya namakan Gold Adult Member. Hal ini karena anggota dari cluster 4 berumur di rentang 20-40 tahun dengan nilai belanja setahunnya di sekitaran 5,5 juta.

Berdasarkan observasi tersebut, saya juga mendapatkan beberapa insight lainnya yakni :
* Member yang paling berharga yakni diamond member ternyata sejauh ini hanya merupakan para pengusaha. Oleh karena itu, saya sarankan untuk memprioritaskan target pemasaran pada para pengusaha mengingat merekalah kelompok yang menyumbangkan nilai belanja paling tinggi pada perusahaan ini.
* Gold member sejauh ini hanya diisi oleh para professional dan ibu rumah tangga, lalu silver member sejauh ini hanya diisi oleh para pelajar dan mahasiswa.
* Pelanggan sejauh ini didominasi oleh wanita dengan persentase 82%. Perbedaannya sangat jauh mengingat persentase pria hanya 18% sehingga bisa jadi secara natural memang kalangan wanitalah yang cenderung tertarik untuk belanja di perusahaan ini. Oleh karena itu, saya sarankan untuk memprioritaskan target pemasaran pada wanita.
* Kalangan yang sebaiknya paling diprioritaskan sebagai target pemasaran adalah para pengusaha wanita.
  
## Memprediksi Segmen pada Data Baru
Model yang sudah dibuat juga dapat digunakan sehari-hari untuk memprediksi segmen pada data-data baru. Dengan kemampuan prediksi tersebut, maka tim bisnis dapat dengan cepat mengetahui segmen dari pelanggan sehingga bisa mengatur strategi marketing dengan lebih efisien.
Berikut ini ada 1 data baru yang akan saya coba prediksikan menggunakan model bernama “kproto” yang tadi dibuat.  
<img src="Customer Segmentation with Python/10.png?raw=true"/>  
Lalu berikut adalah hasil prediksi segmennya :  
<img src="Customer Segmentation with Python/11.png?raw=true"/>  
Tampak bahwa model memprediksikan bahwa data baru tersebut bersegmen Diamond Senior Member. Untuk selanjutnya, prediksi segmen dapat dilakukan secara real-time yakni setiap ada data baru yang masuk atau secara batch, misal satu hari sekali.  
  
Demikian proyek segmentasi pelanggan yang saya buat. Akhir kata, wassalamu’alaykum warahmatullahi wabarakatuh.

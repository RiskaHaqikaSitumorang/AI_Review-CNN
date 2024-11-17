# Review CNN serta penjelsan code dan output pada link 2 dan 3

## Deep Learning: Convolutional Neural Networks [link1](https://www.megabagus.id/deep-learning-convolutional-neural-networks/)

Convolutional Neural Network (CNN) adalah jenis jaringan saraf tiruan yang digunakan untuk pengolahan data berbentuk gambar atau video. CNN bekerja dengan cara mengekstrak fitur dari gambar melalui proses yang disebut convolution, di mana gambar diproses menggunakan filter atau feature detector untuk mendeteksi pola-pola tertentu, seperti garis, sudut, atau bentuk. Proses ini diikuti dengan activation function seperti ReLU untuk mengurangi linearitas data, serta max pooling untuk mempertahankan fitur yang paling penting dan mengurangi dimensi gambar.
#### Penerapan CNN di Dunia Nyata:
1. Facebook menggunakan CNN untuk pengenalan wajah otomatis pada foto yang diunggah pengguna.
2. CCTV di negara maju sering memanfaatkan CNN untuk deteksi wajah secara real-time, mendukung keamanan dan identifikasi orang.
#### Cara Kerja CNN
1. CNN meniru cara manusia mengenali objek visual dengan proses training, yaitu mempelajari dari dataset gambar yang diberikan, sehingga mampu membedakan objek (misalnya, kucing vs. anjing).
2. Tingkat akurasi CNN tergantung pada kualitas dataset yang digunakan. Gambar yang kurang jelas bisa menurunkan akurasi prediksi.

## Deep Learning: Convolutional Neural Networks (aplikasi) [link2](https://www.megabagus.id/deep-learning-convolutional-neural-networks-aplikasi)

Tujuannya adalah melakukan klasifikasi gambar kucing dan anjing. Dataset yang digunakan terdiri dari 8,000 gambar untuk training set (4,000 gambar kucing dan 4,000 gambar anjing) dan 2,000 gambar untuk test set (1,000 gambar kucing dan 1,000 gambar anjing). 

## 📊 Performance Results
![Screenshot 2024-11-17 230700](https://github.com/user-attachments/assets/49a4dbae-a140-47cc-9e7d-f97c0f019bb1)

1. Akurasi dan loss validation menunjukkan beberapa naik-turun pada pertengahan epoch, tetapi stabil pada akhir training.
2. Model menunjukkan tanda-tanda peningkatan performa setelah pertengahan epoch, dengan akurasi yang konsisten tinggi.
3. Nilai accuracy meningkat secara bertahap, dan nilai loss menurun seiring waktu walaupun tidak konssten.
4. Model berhasil meningkatkan performanya secara bertahap, meskipun ada beberapa masalah pada dataset di awal training. Peningkatan akurasi validation yang tinggi pada epoch terakhir menunjukkan bahwa model telah mencapai performa yang baik pada data validation.

![Screenshot 2024-11-17 230925](https://github.com/user-attachments/assets/bf287897-19da-4a4c-a4ef-b03c82ba2c4a)

1. Model ini sangat cepat dalam memproses gambar satu per satu, dengan waktu eksekusi rata-rata hanya sekitar puluhan milidetik per gambar. Ini menunjukkan efisiensi model dan kemungkinan optimasi pada perangkat keras yang digunakan (seperti penggunaan GPU).
2. Terdapat 921 gambar yang diprediksi sebagai "dog".
3. Terdapat 79 gambar yang diprediksi sebagai "cat".


## Modul Lab Machine Learning #6  [link3](https://modul-praktikum-ai.vercel.app/Materi/4-convolutional-neural-network)
Modul ini menggunakan dataset CIFAR-10, yang terdiri dari 60,000 gambar dalam 10 kelas, kita dapat melatih model CNN untuk mengenali gambar dan kemudian membuat prediksi berdasarkan gambar yang belum dilihat sebelumnya.

## 📊 Performance Results

![Screenshot 2024-11-17 231021](https://github.com/user-attachments/assets/4264ae63-6ac3-4622-b358-d924f21cca20)

1. Akurasi: Model menunjukkan peningkatan akurasi pada data pelatihan dari 27.78% pada epoch pertama menjadi 74.10% pada epoch terakhir.
2. Loss: Nilai loss menurun secara konsisten dari 1.92 pada epoch pertama menjadi 0.74 pada epoch terakhir, menunjukkan bahwa model semakin baik dalam memprediksi.
3. Akurasi Validasi: Akurasi validasi juga meningkat dari 50.45% pada epoch pertama menjadi 72.08% pada epoch terakhir.
4. Loss Validasi: Nilai loss validasi juga menunjukkan penurunan dari 1.39 menjadi 0.83, meskipun ada sedikit fluktuasi pada beberapa epoch.
5. Model menunjukkan peningkatan yang stabil dalam akurasi dan penurunan loss baik pada data pelatihan maupun validasi.
6. Proses pelatihan berjalan efisien dengan waktu yang relatif konstan per epoch.

![Screenshot 2024-11-17 231051](https://github.com/user-attachments/assets/06e37226-39bc-4eab-b1f0-1d8a6865ab76)

1. Akurasi Pengujian: Model mencapai akurasi sekitar 72.08% pada data uji (test set).
2. Loss Pengujian: Loss model pada data uji adalah 0.82.
3. Waktu Pengujian: Pengujian model dilakukan dalam waktu 4 detik dengan waktu rata-rata 12 ms per langkah (step).
4. Model menunjukkan akurasi yang cukup baik pada data uji, dengan sedikit penurunan dibandingkan akurasi pelatihan.
5. Loss pada data uji menunjukkan hasil yang stabil.

![Screenshot 2024-11-17 231127](https://github.com/user-attachments/assets/b3ebbae7-3110-4411-be23-36556e7d1cd3)

1. Gambar tersebut diprediksi sebagai "cat" (kucing), yang sesuai dengan konten gambar yang saya upload yaitu kucing.
2. Indeks kelas yang diprediksi adalah 3, yang sesuai dengan kelas "cat" pada dataset CIFAR-10.
3. Model berhasil mengenali gambar kucing dengan akurat berdasarkan prediksi yang dibuat.













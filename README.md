# Review CNN serta penjelsan code dan output pada link 2 dan 3

## [[1]](https://www.megabagus.id/deep-learning-convolutional-neural-networks/) Deep Learning: Convolutional Neural Networks 

Convolutional Neural Network (CNN) adalah jenis jaringan saraf tiruan yang digunakan untuk pengolahan data berbentuk gambar atau video. CNN bekerja dengan cara mengekstrak fitur dari gambar melalui proses yang disebut convolution, di mana gambar diproses menggunakan filter atau feature detector untuk mendeteksi pola-pola tertentu, seperti garis, sudut, atau bentuk. Proses ini diikuti dengan activation function seperti ReLU untuk mengurangi linearitas data, serta max pooling untuk mempertahankan fitur yang paling penting dan mengurangi dimensi gambar.
#### Penerapan CNN di Dunia Nyata:
1. Facebook menggunakan CNN untuk pengenalan wajah otomatis pada foto yang diunggah pengguna.
2. CCTV di negara maju sering memanfaatkan CNN untuk deteksi wajah secara real-time, mendukung keamanan dan identifikasi orang.
#### Cara Kerja CNN
1. CNN meniru cara manusia mengenali objek visual dengan proses training, yaitu mempelajari dari dataset gambar yang diberikan, sehingga mampu membedakan objek (misalnya, kucing vs. anjing).
2. Tingkat akurasi CNN tergantung pada kualitas dataset yang digunakan. Gambar yang kurang jelas bisa menurunkan akurasi prediksi.

## [[2]](https://www.megabagus.id/deep-learning-convolutional-neural-networks-aplikasi) Deep Learning: Convolutional Neural Networks (aplikasi) 

Tujuannya adalah melakukan klasifikasi gambar kucing dan anjing. Dataset yang digunakan terdiri dari 8,000 gambar untuk training set (4,000 gambar kucing dan 4,000 gambar anjing) dan 2,000 gambar untuk test set (1,000 gambar kucing dan 1,000 gambar anjing). 

## 🧩 penjelasan kode

![image](https://github.com/user-attachments/assets/3098c04d-dd00-48a9-8bfe-9bfab59b58b9)

Kode ini mengimpor beberapa modul yang diperlukan dari TensorFlow Keras. Sequential digunakan untuk membuat model CNN secara berurutan, sedangkan Conv2D, MaxPooling2D, Flatten, dan Dense adalah layer-layer yang akan digunakan dalam model.
![image](https://github.com/user-attachments/assets/7cced315-2246-437d-adb7-52f094876bf9)

Membuat model CNN (Convolutional Neural Network) menggunakan Sequential, di mana layer-layer akan ditambahkan satu per satu.
![image](https://github.com/user-attachments/assets/818a4e70-d2de-4d2b-beab-ba13d40fd92d)

Menambahkan layer convolution pertama dengan 32 filter, ukuran kernel 3x3, dan fungsi aktivasi ReLU. input_shape adalah ukuran input gambar yang diharapkan (128x128 piksel dengan 3 channel warna RGB).
![image](https://github.com/user-attachments/assets/4b9e93bd-d354-49d7-82c0-60c5dc7efa25)

Menambahkan layer pooling untuk mengurangi dimensi gambar dan menjaga fitur penting. pool_size (2x2) berarti mengurangi ukuran gambar dengan mengambil nilai maksimum di dalam jendela 2x2. Menambahkan layer convolution kedua dengan konfigurasi yang sama seperti layer pertama (32 filter, ukuran kernel 3x3) dan layer pooling 2x2.

![image](https://github.com/user-attachments/assets/8820bad4-e4be-4d23-a768-8a780e0a0d58)

Meratakan hasil dari layer sebelumnya menjadi satu vektor yang panjang untuk memasukkannya ke dalam jaringan saraf fully connected.
![image](https://github.com/user-attachments/assets/7e9875e5-8f56-4285-af6b-974cb5bc6228)

Menambahkan dua layer fully connected:
1. Layer pertama memiliki 128 neuron dengan fungsi aktivasi ReLU.
2. Layer kedua adalah layer output dengan satu neuron dan fungsi aktivasi sigmoid, digunakan untuk klasifikasi biner (binary classification).

![image](https://github.com/user-attachments/assets/575a9c64-2b3e-4380-9454-ee2ed1a91987)

Mengompilasi model dengan optimizer adam, fungsi loss binary_crossentropy (karena klasifikasi biner), dan metrik accuracy untuk mengevaluasi kinerja model.

![image](https://github.com/user-attachments/assets/1321a929-9b1e-4b38-a33a-ca9983783325)

Mengimpor ImageDataGenerator untuk mengolah data gambar. Data pelatihan (train_datagen) di-normalisasi dengan rescale dan diberi augmentasi seperti shear_range, zoom_range, dan horizontal_flip untuk memperbesar variasi data pelatihan. Data pengujian (test_datagen) hanya di-normalisasi dengan rescale.


![image](https://github.com/user-attachments/assets/c70ba567-a247-4da9-bdf4-6166a426144a)

Membuat data generator dari direktori untuk set pelatihan dan pengujian. Gambar diubah ukurannya menjadi 128x128, batch_size ditentukan sebagai 32, dan class_mode diset ke binary untuk klasifikasi biner.


![image](https://github.com/user-attachments/assets/260c30d1-754d-4163-b649-a19dcdc80230)

Melatih model dengan data pelatihan selama 50 epoch. steps_per_epoch dan validation_steps ditentukan dengan membagi jumlah data dengan ukuran batch (menggunakan // untuk pembagian integer).



![image](https://github.com/user-attachments/assets/a1a08ca9-4480-45c0-bcc0-60e1e1a8dc27)

Menggunakan model yang telah dilatih untuk memprediksi apakah gambar termasuk kategori 'cat' atau 'dog'. Untuk setiap gambar dalam rentang nomor 4001 hingga 5000, model memuat gambar, mengubah ukurannya, dan memprediksi kelasnya.



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


## [[3]](https://modul-praktikum-ai.vercel.app/Materi/4-convolutional-neural-network) Modul Lab Machine Learning #6  
Modul ini menggunakan dataset CIFAR-10, yang terdiri dari 60,000 gambar dalam 10 kelas, kita dapat melatih model CNN untuk mengenali gambar dan kemudian membuat prediksi berdasarkan gambar yang belum dilihat sebelumnya.

## 🧩 Penjelasan Kode
![image](https://github.com/user-attachments/assets/1c2f4791-ca0f-4fdf-a58a-08515fbb3c78)
- Mengimpor TensorFlow untuk membangun dan melatih model.
- Mengimpor dataset CIFAR-10, yang berisi gambar berwarna (32x32 piksel) dari 10 kelas berbeda.
- Menggunakan to_categorical untuk mengonversi label menjadi format one-hot encoding.

![image](https://github.com/user-attachments/assets/fcef8008-5428-496e-b7de-77fbe099ec3b)
- cifar10.load_data() mengembalikan dataset yang sudah dipisahkan menjadi data pelatihan dan data pengujian.
- train_images dan test_images menyimpan gambar, sedangkan train_labels dan test_labels menyimpan label kelas untuk setiap gambar.
  
![image](https://github.com/user-attachments/assets/652da511-d489-42f8-8ada-77d7143f1a77)
- Gambar di-normalisasi ke rentang 0 hingga 1 dengan membagi setiap piksel dengan 255.0.
- Normalisasi mempercepat pelatihan dan meningkatkan akurasi model.

![image](https://github.com/user-attachments/assets/16190692-96f0-4c2c-be84-7c75510e3b5f)
- Label dikonversi menjadi one-hot encoding (contoh: label 3 menjadi [0, 0, 0, 1, 0, 0, 0, 0, 0, 0]), dengan 10 kelas.

![image](https://github.com/user-attachments/assets/856e8753-0f4d-4f1e-a5d2-0483793822c2)
- Membuat model menggunakan Sequential API dari Keras.
- Menambahkan tiga lapisan konvolusi dengan jumlah filter yang meningkat dari 32 → 64 → 128.
     - Conv2D: Lapisan konvolusi yang memproses fitur gambar.
     - MaxPooling2D: Mengurangi ukuran fitur menggunakan max pooling untuk meminimalisasi overfitting.
- Flatten: Meratakan data dari 2D ke 1D untuk input ke lapisan Dense.
- Dense: Menambahkan lapisan fully connected dengan 128 neuron dan fungsi aktivasi relu.
- Dropout: Mencegah overfitting dengan menonaktifkan 50% neuron secara acak selama pelatihan.
- Layer output menggunakan softmax karena ada 10 kelas yang ingin diprediksi.

![image](https://github.com/user-attachments/assets/d3e5a1b9-8037-4039-a47d-b513425f1a59)
- optimizer='adam': Menggunakan algoritma optimasi Adam untuk memperbarui bobot.
- loss='categorical_crossentropy': Fungsi loss yang cocok untuk masalah klasifikasi multi-kelas.
- metrics=['accuracy']: Menggunakan akurasi sebagai metrik evaluasi.

![image](https://github.com/user-attachments/assets/b4cef1c2-429a-420d-adaa-d6eadaa50b6e)
- Melatih model menggunakan 10 epoch dengan 64 gambar per batch.
- Validasi dilakukan menggunakan validation_data untuk mengukur performa di setiap epoch.

![image](https://github.com/user-attachments/assets/8bfbf73b-7e0b-4d82-a376-77b08562a4f2)
- Mengevaluasi performa model pada data pengujian dan menampilkan akurasinya.
  
![image](https://github.com/user-attachments/assets/f32d8369-c684-4399-bb2e-2a6f51d0b5db)
- Mengimpor library tambahan untuk memuat gambar, serta memproses dan memprediksi kelasnya.

![image](https://github.com/user-attachments/assets/65a310a6-55a5-459b-b70f-59ffa7ededc3)
- Fungsi untuk memuat gambar dari file, mengubah ukurannya menjadi 32x32, menormalisasinya, dan menambahkan dimensi batch untuk input ke model.

![image](https://github.com/user-attachments/assets/9b64016d-d1ae-4a50-9826-8e7bbca01991)
- Daftar nama kelas dalam dataset CIFAR-10.
- Mengunggah gambar dan menggunakan model untuk memprediksi kelas.
- np.argmax(prediction, axis=1)[0] memilih indeks dengan probabilitas tertinggi yang menunjukkan kelas prediksi.
- Nama kelas ditampilkan berdasarkan hasil prediksi.

  
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













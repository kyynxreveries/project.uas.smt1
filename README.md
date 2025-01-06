### Nama  :Rizky Maulana
### Kelas :Ti.24.A.3
### Nim   :312410430

**Project praktikum ulangan akhir semester**

**"Sistem Kasir Sederhana dengan Diskon Menggunakan Konsep OOP dan Modularisasi"**

Judul ini mencerminkan elemen-elemen penting dari program:
- **Sistem Kasir**: Karena program ini digunakan untuk menghitung transaksi kasir.
- **Sederhana**: Menunjukkan bahwa ini adalah versi dasar dari sistem kasir, tidak terlalu kompleks.
- **Diskon**: Menyebutkan fitur diskon yang ada dalam perhitungan.
- **OOP**: Menunjukkan bahwa program dibangun dengan prinsip Pemrograman Berorientasi Objek.
- **Modularisasi**: Menekankan pada desain yang terstruktur dan terpisah sesuai dengan fungsinya (Data, Process, dan View).

Program ini menggunakan konsep *Object-Oriented Programming (OOP)* dan *modularisasi*. Penjelasan ini bertujuan agar Anda dapat memahami maksud setiap bagian dari kode.

---

### Langkah 1: *Import dan Deklarasi Class*
Kita mulai dengan mendeklarasikan tiga class utama:
1. *Class Data* - untuk menyimpan informasi tentang transaksi (barang yang dibeli).
2. *Class Process* - untuk melakukan perhitungan seperti total harga, diskon, dan harga akhir.
3. *Class View* - untuk menangani input pengguna dan menampilkan hasil ke pengguna.

---

### *Class Data*

![kode program 1](https://github.com/user-attachments/assets/ffd979c4-099a-458c-b9c9-91c5b71387b9)

#### Penjelasan:
- *__init__(self): Ini adalah metode konstruktor untuk menginisialisasi objek **Data*. Pada awalnya, daftar items kosong dan total_price diset ke 0.
- *items*: Menyimpan barang yang dibeli. Setiap barang berupa dictionary dengan atribut nama, harga, dan jumlah.
- *total_price*: Menyimpan jumlah total harga dari semua barang yang dibeli.

---

![kode program 2](https://github.com/user-attachments/assets/d83e4e94-1f9d-40c1-98ad-d01060d46054)

#### Penjelasan:
- *add_item(self, name, price, quantity)*: Metode ini digunakan untuk menambahkan barang yang dibeli ke dalam daftar items. Setiap barang disimpan sebagai dictionary dengan kunci name, price, dan quantity.
- Barang yang baru dimasukkan akan menambah total_price, yaitu harga barang dikali dengan jumlah barang.

---

![kode program 3](https://github.com/user-attachments/assets/33dc18c5-c0f0-46e9-91e0-ff3f1d833dc9)

#### Penjelasan:
- *get_items(self)*: Metode ini digunakan untuk mengembalikan semua barang yang ada dalam daftar items.

---

![kode program 4](https://github.com/user-attachments/assets/f83047b9-4b0e-48a9-bbad-b151f38fb93e)

#### Penjelasan:
- *get_total_price(self)*: Metode ini digunakan untuk mengembalikan total harga dari semua barang yang dibeli, yang telah dihitung sebelumnya.

---

### Langkah 2 *Class Process*

![kode program 5](https://github.com/user-attachments/assets/4b1c44cd-456f-4cc1-9d34-a250b0a7363e)

#### Penjelasan:
- *__init__(self, data): Konstruktor yang menerima objek **Data* sebagai argumen. Objek *Data* ini akan digunakan dalam proses perhitungan.
- *self.data: Menyimpan objek **Data* untuk digunakan dalam perhitungan.

---

![kode program 6](https://github.com/user-attachments/assets/9bcbeef6-3531-4145-b619-2fd065e3d1db)

#### Penjelasan:
- *calculate_discount(self, discount_percentage)*: Metode ini digunakan untuk menghitung nilai diskon. Diskon dihitung dengan mengalikan total_price dengan persentase diskon yang diberikan.
- *total*: Mendapatkan total harga barang yang dibeli dengan memanggil self.data.get_total_price().

---

![kode program 7](https://github.com/user-attachments/assets/853ed45f-6d41-4609-b024-7c9d47687be7)

#### Penjelasan:
- *calculate_final_price(self, discount_percentage)*: Metode ini digunakan untuk menghitung harga akhir setelah diskon. 
  - Pertama, menghitung diskon dengan memanggil calculate_discount.
  - Kedua, mengurangi total harga dengan diskon untuk mendapatkan harga akhir yang harus dibayar.

---

### *Class View*

![kode program 8](https://github.com/user-attachments/assets/596cdb36-4d92-4d43-afd6-5ef2a27dcaac)

#### Penjelasan:
- *__init__(self): Konstruktor ini menginisialisasi objek **Data* dan *Process*.
- *self.data: Objek **Data* untuk menyimpan semua barang yang dibeli.
- *self.process: Objek **Process* yang bertugas untuk melakukan perhitungan transaksi.

---

![kode program 9](https://github.com/user-attachments/assets/2f3ab2f8-3de6-4abf-875e-0a66e30e250d)

#### Penjelasan:
- *get_user_input(self)*: Metode ini digunakan untuk meminta input dari pengguna.
  - *name*: Meminta nama barang yang akan dibeli.
  - *price*: Meminta harga barang, dan mengubah input menjadi tipe data float.
  - *quantity*: Meminta jumlah barang, dan mengubah input menjadi tipe data int.
  - *self.data.add_item(name, price, quantity)*: Menambahkan barang ke dalam daftar transaksi.
  - Program akan terus meminta input sampai pengguna mengetik "selesai".
  - *try-except*: Digunakan untuk menangani kesalahan jika pengguna memasukkan input yang tidak valid (misalnya bukan angka).

---

![kode program 10](https://github.com/user-attachments/assets/35fef6b8-ac24-4697-8a8e-4781e1695b43)

#### Penjelasan:
- *display_receipt(self, discount_percentage)*: Metode ini akan menampilkan struk pembelian kepada pengguna.
  - *items*: Mengambil daftar barang yang dibeli.
  - *total_price*: Mendapatkan total harga dari semua barang yang dibeli.
  - *final_price*: Menghitung harga akhir setelah diskon.
  - *discount*: Menghitung diskon yang diberikan.

---

![kode program 11](https://github.com/user-attachments/assets/36378451-62ea-4289-9b38-6addbf8ef7d7)

#### Penjelasan:
- Bagian ini menampilkan header tabel yang terstruktur. Nama kolom diatur agar terlihat rapi dengan menggunakan format string (<20, <10).

---

![kode program 12](https://github.com/user-attachments/assets/6cea8182-d660-4d92-8121-ee5e2528bd54)

#### Penjelasan:
- *for item in items*: Menampilkan setiap barang dalam tabel.
  - *total_item_price*: Menghitung harga total untuk masing-masing barang (harga * jumlah).
  - Menampilkan setiap baris untuk setiap barang yang dibeli dalam format tabel.

---

![kode program 14](https://github.com/user-attachments/assets/968b5480-01f0-4649-8353-d726afedaa08)

#### Penjelasan:
- Menampilkan total harga, diskon, dan harga akhir yang harus dibayar, dengan format yang konsisten.

---

![kode program 15](https://github.com/user-attachments/assets/ed2593ca-1afa-4ad8-90ae-70ed7259e33f)

#### Penjelasan:
- *run(self)*: Menggabungkan seluruh proses.
  - Meminta input dari pengguna.
  - Meminta input diskon dan menghitung hasil perhitungan.
  - Menampilkan struk pembelian.
  - Jika input diskon tidak valid, maka diskon dianggap 0%.

---

### Langkah 3: Program Utama

![kode program 16](https://github.com/user-attachments/assets/2967f3ef-f47f-4fe0-ada2-e3120cea8dc3)

#### Penjelasan:
- *if __name__ == "__main__":*: Menyatakan bahwa program akan berjalan saat file ini dijalankan langsung.
- Membuat objek *View* dan menjalankan program dengan metode *run()*.

---

### Langkah Terakhir: Hasil Program

![Hasil Program](https://github.com/user-attachments/assets/90ee5a69-86dd-4a50-92ee-9aa4e34d3466)
![Hasil Program (2)](https://github.com/user-attachments/assets/6054072e-24a7-42a7-abea-17f7f90cb75a)


### Kesimpulan:
Program ini mengimplementasikan *OOP (Object-Oriented Programming)* dengan cara yang modular. Setiap bagian program bertanggung jawab untuk satu tugas:
- *Class Data* menyimpan data transaksi.
- *Class Process* melakukan perhitungan.
- *Class View* menangani antarmuka pengguna dan menampilkan hasilnya.

Dengan pendekatan ini, program menjadi mudah dibaca, dimodifikasi, dan diperluas sesuai kebutuhan.



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

![Screenshot 2025-01-04 153751](https://github.com/user-attachments/assets/3c13a6d2-d03c-4178-9093-3f1b0cc48b38)

#### Penjelasan:
- *__init__(self): Ini adalah metode konstruktor untuk menginisialisasi objek **Data*. Pada awalnya, daftar items kosong dan total_price diset ke 0.
- *items*: Menyimpan barang yang dibeli. Setiap barang berupa dictionary dengan atribut nama, harga, dan jumlah.
- *total_price*: Menyimpan jumlah total harga dari semua barang yang dibeli.

---

![Screenshot 2025-01-04 154144](https://github.com/user-attachments/assets/d2a3dd2e-68af-4448-b922-7921af889c8e)

#### Penjelasan:
- *add_item(self, name, price, quantity)*: Metode ini digunakan untuk menambahkan barang yang dibeli ke dalam daftar items. Setiap barang disimpan sebagai dictionary dengan kunci name, price, dan quantity.
- Barang yang baru dimasukkan akan menambah total_price, yaitu harga barang dikali dengan jumlah barang.

---

![Screenshot 2025-01-04 154328](https://github.com/user-attachments/assets/750b3696-a21c-4207-8ae0-aa61f5ee25ef)

#### Penjelasan:
- *get_items(self)*: Metode ini digunakan untuk mengembalikan semua barang yang ada dalam daftar items.

---

![Screenshot 2025-01-04 154453](https://github.com/user-attachments/assets/515dbbb4-9564-4e57-8460-dc6c7a10b04c)

#### Penjelasan:
- *get_total_price(self)*: Metode ini digunakan untuk mengembalikan total harga dari semua barang yang dibeli, yang telah dihitung sebelumnya.

---

### Langkah 2 *Class Process*

![Screenshot 2025-01-04 154558](https://github.com/user-attachments/assets/7c42c26c-00b7-4d54-baac-78d6cee41998)

#### Penjelasan:
- *__init__(self, data): Konstruktor yang menerima objek **Data* sebagai argumen. Objek *Data* ini akan digunakan dalam proses perhitungan.
- *self.data: Menyimpan objek **Data* untuk digunakan dalam perhitungan.

---

![Screenshot 2025-01-04 154819](https://github.com/user-attachments/assets/c643e594-f358-4898-a8e9-e22e5e976839)

#### Penjelasan:
- *calculate_discount(self, discount_percentage)*: Metode ini digunakan untuk menghitung nilai diskon. Diskon dihitung dengan mengalikan total_price dengan persentase diskon yang diberikan.
- *total*: Mendapatkan total harga barang yang dibeli dengan memanggil self.data.get_total_price().

---

![Screenshot 2025-01-04 155102](https://github.com/user-attachments/assets/4a361779-c3ea-4db5-9b04-3776acec5849)

#### Penjelasan:
- *calculate_final_price(self, discount_percentage)*: Metode ini digunakan untuk menghitung harga akhir setelah diskon. 
  - Pertama, menghitung diskon dengan memanggil calculate_discount.
  - Kedua, mengurangi total harga dengan diskon untuk mendapatkan harga akhir yang harus dibayar.

---

### *Class View*

![Screenshot 2025-01-04 155307](https://github.com/user-attachments/assets/b6d3a7c3-607b-486d-9117-45a5752ea8e1)

#### Penjelasan:
- *__init__(self): Konstruktor ini menginisialisasi objek **Data* dan *Process*.
- *self.data: Objek **Data* untuk menyimpan semua barang yang dibeli.
- *self.process: Objek **Process* yang bertugas untuk melakukan perhitungan transaksi.

---

![Screenshot 2025-01-04 155455](https://github.com/user-attachments/assets/faf88f06-df8b-4811-a73f-34ca419d3ed2)

#### Penjelasan:
- *get_user_input(self)*: Metode ini digunakan untuk meminta input dari pengguna.
  - *name*: Meminta nama barang yang akan dibeli.
  - *price*: Meminta harga barang, dan mengubah input menjadi tipe data float.
  - *quantity*: Meminta jumlah barang, dan mengubah input menjadi tipe data int.
  - *self.data.add_item(name, price, quantity)*: Menambahkan barang ke dalam daftar transaksi.
  - Program akan terus meminta input sampai pengguna mengetik "selesai".
  - *try-except*: Digunakan untuk menangani kesalahan jika pengguna memasukkan input yang tidak valid (misalnya bukan angka).

---

![Screenshot 2025-01-04 155551](https://github.com/user-attachments/assets/ff5b3f0e-9d23-4f29-845e-1c0efe8d308f)

#### Penjelasan:
- *display_receipt(self, discount_percentage)*: Metode ini akan menampilkan struk pembelian kepada pengguna.
  - *items*: Mengambil daftar barang yang dibeli.
  - *total_price*: Mendapatkan total harga dari semua barang yang dibeli.
  - *final_price*: Menghitung harga akhir setelah diskon.
  - *discount*: Menghitung diskon yang diberikan.

---

![Screenshot 2025-01-04 155704](https://github.com/user-attachments/assets/142b8a62-392d-4490-b287-ae647c458e25)

#### Penjelasan:
- Bagian ini menampilkan header tabel yang terstruktur. Nama kolom diatur agar terlihat rapi dengan menggunakan format string (<20, <10).

---

![Screenshot 2025-01-04 155800](https://github.com/user-attachments/assets/ea4a4368-6668-4687-87e1-4212ef601c91)

#### Penjelasan:
- *for item in items*: Menampilkan setiap barang dalam tabel.
  - *total_item_price*: Menghitung harga total untuk masing-masing barang (harga * jumlah).
  - Menampilkan setiap baris untuk setiap barang yang dibeli dalam format tabel.

---

![Screenshot 2025-01-04 155903](https://github.com/user-attachments/assets/97d4d439-320b-4996-ae2c-d7e4ebc1789d)

#### Penjelasan:
- Menampilkan total harga, diskon, dan harga akhir yang harus dibayar, dengan format yang konsisten.

---

![Screenshot 2025-01-04 155951](https://github.com/user-attachments/assets/760be2a7-b8a7-4a7b-9623-a76c3f4e325d)

#### Penjelasan:
- *run(self)*: Menggabungkan seluruh proses.
  - Meminta input dari pengguna.
  - Meminta input diskon dan menghitung hasil perhitungan.
  - Menampilkan struk pembelian.
  - Jika input diskon tidak valid, maka diskon dianggap 0%.

---

### Langkah 3: Program Utama

![Screenshot 2025-01-04 160048](https://github.com/user-attachments/assets/3cb9b340-8281-455e-a918-15f95aff3271)

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



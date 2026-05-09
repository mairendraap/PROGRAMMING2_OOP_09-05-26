# PROGRAMMING 2 - OBJECT ORIENTED PROGRAMMING
## Herdan Wahyu Mairendra Pangestu_3325600064

Dokumentasi ini mencakup penjelasan saya tentang logika, sintaks, dan penerapan konsep Object-Oriented Programming (OOP) untuk Latihan 2a, 2b, 3a, dan 3b.

## 1. Struktur Class dan Logika Program

Sistem ini dibangun menggunakan tiga class utama yang saling berinteraksi:

### A. Class DataRecord
**Logika:** Berperan sebagai model data (blueprint) untuk satu entri penjualan.
- **Atribut:** `name` (nama produk), `qty` (jumlah), dan `price` (harga).
- **Special Method:** Menggunakan `__str__` untuk merepresentasikan objek sebagai string yang rapi saat dicetak.

### B. Class Dataset
**Logika:** Berperan sebagai kontainer atau wadah untuk mengelola sekumpulan objek `DataRecord`.
- **load_data_from_file:** Membaca file teks, melakukan parsing (pemisahan string), dan mengubah setiap baris menjadi objek `DataRecord`.
- **add_data:** Menambahkan data baru dengan validasi tipe data (memastikan hanya objek `DataRecord` yang masuk).
- **display_data:** Melakukan iterasi pada list `records` untuk menampilkan seluruh data.

### C. Class DataAnalyzer
**Logika:** Berperan sebagai mesin pemroses data (logic layer) yang menerima objek `Dataset` untuk dianalisis.
- **Statistik:** Menghitung total uang (dengan/tanpa pajak), mencari item dengan kuantitas tertinggi, dan menghitung rata-rata harga.

---

## 2. Penjelasan Konsep OOP yang Digunakan

Proyek ini menerapkan pilar-pilar utama OOP:

1.  **Encapsulation (Enkapsulasi):** Data (`records`, `name`, `price`) dan fungsi yang memanipulasinya dibungkus dalam satu unit (Class). Misalnya, variabel `records` hanya dimanipulasi melalui method `add_data` atau `load_data_from_file`.
2.  **Abstraction (Abstraksi):** Pengguna class `DataAnalyzer` tidak perlu tahu bagaimana cara rumit menghitung pajak atau mencari nilai maksimum; mereka cukup memanggil method `calculate_total_sales()`.
3.  **Object Interaction:** Bagaimana `DataAnalyzer` menerima objek `Dataset` sebagai parameter (`self.dataset = dataset`) menunjukkan cara objek berkomunikasi satu sama lain.
4.  **Validation:** Penggunaan `isinstance(record, DataRecord)` memastikan integritas data, salah satu praktik terbaik dalam OOP untuk menjaga keamanan objek.

---

## 3. Sintaks Python yang Digunakan

| Sintaks | Kegunaan |
| :--- | :--- |
| `class Name:` | Mendefinisikan blueprint objek. |
| `def __init__(self, ...):` | Constructor untuk inisialisasi atribut saat objek dibuat. |
| `self` | Referensi ke instance objek itu sendiri untuk mengakses atribut/method. |
| `with open(file, 'r') as f:` | Context manager untuk membaca file secara aman. |
| `f-strings (f"...")` | Memformat string dengan variabel secara ringkas. |
| `isinstance(obj, Class)` | Mengecek apakah sebuah variabel adalah instance dari class tertentu. |
| `enumerate(list, 1)` | Melakukan looping sekaligus mendapatkan nomor urut mulai dari 1. |
| `list.append()` | Menambahkan elemen ke dalam list `records`. |

---

## 4. Cara Menjalankan di Google Colab

1.  Buat kode class (`DataRecord`, `Dataset`, `DataAnalyzer`) ke dalam satu cell.
2.  Buat file testing (misal: `data_penjualan.txt`) menggunakan kode Python atau upload manual.
3.  Jalankan script utama untuk melihat hasil analisis di console.

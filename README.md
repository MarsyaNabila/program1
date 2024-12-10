# TUGAS PRATIKUM 8
# Data Diri
Nama: MARSYA NABILA PUTRI 

Kelas: TI.24.A.4

NIM: 312410338

# Proyek Mahasiswa - Sistem Informasi Mahasiswa
Ini adalah contoh proyek Python yang menggunakan konsep Object-Oriented Programming (OOP) untuk mengelola data mahasiswa.
# Struktur Folder
Berikut adalah struktur folder proyek ini:

```python
├── view/
│   ├── mahasiswa.py  # Menampilkan data mahasiswa
│   ├── __init__.py   # Inisialisasi folder view sebagai package
├── data/
│   ├── mahasiswa.py  # Menyimpan data mahasiswa dan definisi class Mahasiswa
│   ├── __init__.py   # Inisialisasi folder data sebagai package
├── main.py  # Program utama untuk menampilkan menu utama
├── __init__.py  # Inisialisasi folder proyek sebagai package
````

# Deskripsi File
# 1. `data/mahasiswa.py`
File ini berisi model data mahasiswa dengan definisi kelas `Mahasiswa` dan `DataMahasiswa`. Kelas `Mahasiswa` berfungsi untuk mendefinisikan informasi mahasiswa seperti ID, nama, dan jurusan. Kelas DataMahasiswa digunakan untuk mengelola data mahasiswa (misalnya, menambah, menghapus, atau memperbarui data).

```python
class Mahasiswa:
    def __init__(self, nim, nama, jurusan):
        self.nim = nim
        self.nama = nama
        self.jurusan = jurusan

    def __str__(self):
        return f"NIM: {self.nim}, Nama: {self.nama}, Jurusan: {self.jurusan}"

class DataMahasiswa:
    def __init__(self):
        self.data = []

    def tambah_data(self, mahasiswa):
        self.data.append(mahasiswa)

    def hapus_data(self, nim):
        self.data = [m for m in self.data if m.nim != nim]

    def ubah_data(self, nim, nama_baru, jurusan_baru):
        for m in self.data:
            if m.nim == nim:
                m.nama = nama_baru
                m.jurusan = jurusan_baru

    def cari_data(self, nim):
        for m in self.data:
            if m.nim == nim:
                return m
        return None

    def tampilkan_semua_data(self):
        return self.data
````

# 2. `view/mahasiswa.py`
File ini berisi kelas `ViewMahasiswa`, yang memiliki metode untuk menampilkan daftar mahasiswa dan detail mahasiswa.

    - `tampilkan_list(data_mahasiswa)` : Menampilkan daftar semua mahasiswa.
    - `tampilkan_detail(mahasiswa)` : Menampilkan detail informasi mahasiswa.

    ```python
    class ViewMahasiswa:
    @staticmethod
    def tampilkan_list(data_mahasiswa):
        if not data_mahasiswa:
            print("Tidak ada data mahasiswa.")
        else:
            print("\n=== Daftar Mahasiswa ===")
            for mahasiswa in data_mahasiswa:
                print(mahasiswa)

    @staticmethod
    def tampilkan_detail(mahasiswa):
        if mahasiswa:
            print("\n=== Detail Mahasiswa ===")
            print(mahasiswa)
        else:
            print("\nMahasiswa tidak ditemukan.")
```





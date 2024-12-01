# Nama : NAUFAL YAZID ALBANI
# Kelas : TI.24.A.4
# NIM : 312410279
# BAHASA PEMOGRAMAN 

# LATIHAN 1

![Screenshot 2024-12-01 183732](https://github.com/user-attachments/assets/bd3dd296-6f9f-44a5-83f3-0d90e4d7ea4a)

# LATIHAN 1.py

```python
import math

a = lambda x: x**2
b = lambda x, y: math.sqrt(x*2 + y*2)
c = lambda *args: sum(args)/len(args) if args else 0
d = lambda s: "".join(set(s)) 

print("lambda a(5):", a(5))
print("lambda b(3, 4):", b(3, 4))
print("lambda c(1, 2, 3, 4, 5):", c(1, 2, 3, 4, 5))
print("lambda d('hello Naufal'):", d("Naufal"))

````
CODE PROGRAM :

![image](https://github.com/user-attachments/assets/ac79ac26-02e0-455a-b6c6-4eb834a9964d)

hasil program tersebut :

![image](https://github.com/user-attachments/assets/1f9ff5bb-3f49-447f-bd95-a4457292a745)

# TUGAS PRAKTIKUM : 

![Screenshot 2024-12-01 184954](https://github.com/user-attachments/assets/de5a14d4-512a-4890-88ef-16133d2b53f1)

# TUGAS PRAKTIKUM.Py :

```python
def tambah():
    """Menambahkan data mahasiswa baru ke dalam daftar."""
    nama = input("Masukkan nama mahasiswa: ")
    if not nama.strip():
        print("Nama tidak boleh kosong.")
        return
    try:
        nilai = int(input("Masukkan nilai mahasiswa: "))
    except ValueError:
        print("Nilai harus berupa angka.")
        return
    daftar_mahasiswa[nama] = nilai
    print("Data mahasiswa berhasil ditambahkan.")

def tampilkan():
    """Menampilkan semua data mahasiswa."""
    if not daftar_mahasiswa:
        print("Daftar mahasiswa kosong.")
    else:
        print("Daftar Mahasiswa:")
        for nama, nilai in daftar_mahasiswa.items():
            print(f"{nama}: {nilai}")

def hapus(nama):
    """Menghapus data mahasiswa berdasarkan nama."""
    if nama in daftar_mahasiswa:
        del daftar_mahasiswa[nama]
        print(f"Data mahasiswa {nama} berhasil dihapus.")
    else:
        print(f"Data mahasiswa {nama} tidak ditemukan.")

def ubah(nama):
    """Mengubah data mahasiswa berdasarkan nama."""
    if nama in daftar_mahasiswa:
        try:
            nilai_baru = int(input(f"Masukkan nilai baru untuk {nama}: "))
            daftar_mahasiswa[nama] = nilai_baru
            print(f"Data mahasiswa {nama} berhasil diubah.")
        except ValueError:
            print("Nilai harus berupa angka.")
    else:
        print(f"Data mahasiswa {nama} tidak ditemukan.")

daftar_mahasiswa = {}

if __name__ == "__main__":
    while True:
        print("\nMenu:")
        print("1. Tambah data")
        print("2. Tampilkan data")
        print("3. Hapus data")
        print("4. Ubah data")
        print("5. Keluar")

        pilihan = input("Pilih menu (1-5): ")

        if pilihan == '1':
            tambah()
        elif pilihan == '2':
            tampilkan()
        elif pilihan == '3':
            nama = input("Masukkan nama mahasiswa yang ingin dihapus: ")
            hapus(nama)
        elif pilihan == '4':
            nama = input("Masukkan nama mahasiswa yang ingin diubah: ")
            ubah(nama)
        elif pilihan == '5':
            print("Terima kasih!")
            break
        else:
            print("Pilihan tidak valid.")

````

# Penjelasan Code : 

```python
"""Menambahkan data mahasiswa baru ke dalam daftar."""
    nama = input("Masukkan nama mahasiswa: ")
    if not nama.strip():
        print("Nama tidak boleh kosong.")
        return
    try:
        nilai = int(input("Masukkan nilai mahasiswa: "))
    except ValueError:
        print("Nilai harus berupa angka.")
        return
    daftar_mahasiswa[nama] = nilai
    print("Data mahasiswa berhasil ditambahkan.")

````
Meminta pengguna untuk memasukan nama mahasiswa.Apabila nama kosong maka klick spasi.Program akan mencetak kesalahan dan keluar dari program tersebut.Menggunakan  `try-except` untuk mengonversi nilai yang dimasukan menjadi integer, apabila gagal program akan mencetak pesan yang tidak valid, jika semua valid data mahasiswa(nama dan nilai) ditambahkan kedalam dictionary `daftar mahasiswa` dan program akan pesan konfirmasi.

```python
def tampilkan():
    """Menampilkan semua data mahasiswa."""
    if not daftar_mahasiswa:
        print("Daftar mahasiswa kosong.")
    else:
        print("Daftar Mahasiswa:")
        for nama, nilai in daftar_mahasiswa.items():
            print(f"{nama}: {nilai}")

````
fungsi ini menampilkan semua data mahasiswa yang ada dalam `daftar mahasiswa` kosong, apabila tidak kosong, mencetak `daftar mahasiswa`.Dan menggunakan loop untuk mencetak setiap nama mahasiswa dan nilai mereka dalam format `nama : nilai`.


```python
def hapus(nama):
    """Menghapus data mahasiswa berdasarkan nama."""
    if nama in daftar_mahasiswa:
        del daftar_mahasiswa[nama]
        print(f"Data mahasiswa {nama} berhasil dihapus.")
    else:
        print(f"Data mahasiswa {nama} tidak ditemukan.")

````
memeriksa nama mahasiswa apakah yang ingin di hapus ada dalam `daftar_mahasiswa` , apabila ada data mahasiswa dihapus menggunakan pesan konfirmasi bahwa data berhasil dihapus, apabila tidak ada maka program akan mencetak pesan bahwa mahasiswa tersebut tidak ditemukan.

```python
def ubah(nama):
    """Mengubah data mahasiswa berdasarkan nama."""
    if nama in daftar_mahasiswa:
        try:
            nilai_baru = int(input(f"Masukkan nilai baru untuk {nama}: "))
            daftar_mahasiswa[nama] = nilai_baru
            print(f"Data mahasiswa {nama} berhasil diubah.")
        except ValueError:
            print("Nilai harus berupa angka.")
    else:
        print(f"Data mahasiswa {nama} tidak ditemukan.")

````

Mnegubah nilai mahasiswa berdasarkan yang di masukan, memeriksa apakah nama mahasiswa ada dalam `daftar_mahasiswa` , apabila ada maka pengguna akan diminta memasukan  nilai baru dan mecoba megonversi nya menjadi `integer`..Jika konversi berhasil maka nilai mahasiswa diperbarui dalam `dictionary` dan mencetak pesan konfirmasi, apabila konversi gagal maka akan mencetak pesan kesalahan.dan apabila nama tidak ditemukan maka pesan akan mencetak bahwa mahasiswa tidak ditemukan.

```pyhton
daftar_mahasiswa = {}

````

`daftar_mahasiswa` adalah `dictionary` kosong yang akan digunakan untuk menyimpan `data_mahasiswa`

```python
if __name__ == "__main__":
    while True:

````
`if __name__ == "__main__":` memastikan bahwa kode didalam blok ini akan dijalankan jika file ini dieksekusi langsung bukan ketika di impor sebagai modul oleh program lain. `while true` loop tak terbatas yang akan terus berjalan apabila perintah break di jalankan.

```python
print("\nMenu:")
        print("1. Tambah data")
        print("2. Tampilkan data")
        print("3. Hapus data")
        print("4. Ubah data")
        print("5. Keluar")

````
Program mencetak menu dengan lima opsi yang dapat dipilih penggguna: 

1. Tambah Data: untuk menambahkan data mahasiswa baru
2. Tampilkan data: untuk menapilkan semua data mahasiswa yang telah dimasukan
3. Hapus data: Menghapuskan data mahasiswa sesuai nama
4. Ubah data: mengubah nilai mahasiswa berdasarkan nama
5. keluar: berhenti dari program

```python
pilihan = input("Pilih menu (1-5): ")

````
Program meminta pengguna untuk memasukan salah satu menu

```python
if pilihan == '1':
            tambah()
        elif pilihan == '2':
            tampilkan()

````
jika pengguna memasukan angka 1 maka fungsi akan `tambah()`, apabila pengguna memasukan angka 2 maka fungsi akan `tampilkan()` untuk menampilkan semua data mahasiswa yang ada dalam  `daftar_mahasiswa`

```python
elif pilihan == '3':
            nama = input("Masukkan nama mahasiswa yang ingin dihapus: ")
            hapus(nama)
        elif pilihan == '4':
            nama = input("Masukkan nama mahasiswa yang ingin diubah: ")
            ubah(nama)

````
Apabila pengguna memasukan angka 3 maka program akan meminta `input` nama mahasiswa yang ingin dihapus, jika pengguna memasukan angka 4 maka program akan meminta `input` nama mahasiswa yang ingin diubah.

```python
elif pilihan == '5':
            print("Terima kasih!")
            break

````
Jika pengguna memasukan angka 5 maka program akan mencetak `terima kasih !` dan keluar dari loop utama dengan menggunakan `break`.

```python
else:
            print("Pilihan tidak valid.")

````
Jika pengguna tidak memasukan angka `1-5` maka program akan menampilkan pesan `pilihan tidak valid`.dan kembali menampilkan menu.

Code program tersebut :

![image](https://github.com/user-attachments/assets/a1454710-bcad-469b-865f-63dde29e07ef)

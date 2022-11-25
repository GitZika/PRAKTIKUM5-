# PRAKITKUM 5


### Nama:Azhyka Rizki Ramadhan

### NIM:312210287

### Kelas:TI 22 A3

## Latihan 

Dictionary adalah Koleksi item yang berasosiasi dimana setiap pasangan terdiri _key_ dan _value_.

_Key_ dan _Value_ sebagai 'Key' : 'Value'

Dictionary ditulis dengan dipisahkan koma dalam ```{}```

```
telepon = {'Jika' : '085840022606', 'Jiro' : '081324526336'}
```

untuk menampilkan kontak 
```
print(telepon['Jika'])
```

---

Untuk menambahkan elemen dictionary 

```
telepon['Asep']
```

---

untuk mengubah dictionary hampir sama dengan menambahkannya

```
telepon['Jiro'] = '081324526336'
```

---

Untuk menampilkan semua nama/key nya menggunakan perintah

```
print(telepon.keys())
```

Output nya akan menghasilkan

<img width="223" alt="first" src="https://user-images.githubusercontent.com/118233561/203963402-d2204129-8794-436a-9ccc-e26a03999d05.png">


---

Untuk menampilkan semua nomor telepon/value

```
print(telepon.values())
```

Output nya akan menghasilkan 

<img width="370" alt="two" src="https://user-images.githubusercontent.com/118233561/203963500-0e689197-c587-4cc4-9e0b-f193b54ceb6b.png">


---

Untuk menampilkan daftar Nama dan Nomor nya gunakan perintah ```for```

```
for nama,nomor in telepon.items():
    print("%s \t| %s " % (nama,nomor))
```

Output nya akan menghasilkan

<img width="139" alt="3" src="https://user-images.githubusercontent.com/118233561/203963539-c063eb0c-c4e5-40c8-94f1-4955c0cd6a8f.png">


---

Hapus kontak Jiro menggunakan

``` 
del telepon['Jiro']
```

Maka kontak Jiro akan terhapus

<img width="145" alt="4" src="https://user-images.githubusercontent.com/118233561/203963570-6c44967c-102f-427e-a5b0-27ae9b35a586.png">


---

## Tugas Praktikum

Buat dictionary kosong
```
mahasiswa = {}
```
- Buat program untuk lihat data nya

```
def show():
    if mahasiswa.items():
        print("Daftar Nilai")
        print("=================================================================================")
        print("| No |      Nama      |     NIM     |  Tugas  |   UTS   |   UAS   |    Akhir    |")
        print("=================================================================================")
        i = 0
        for a in mahasiswa.items():
            i += 1
            print("| {no:2d} | {0:14s} | {1:11s} | {2:7d} | {3:7d} | {4:7d} |      {5:6.2f} |"
            .format (a[0][: 14],a[1][0],a[1][1],a[1][2],a[1][3],a[1][4], no = i))
        print("=================================================================================")
        
    else:
        print("Daftar Nilai")
        print("=================================================================================")
        print("| No |      Nama      |     NIM     |  Tugas  |   UTS   |   UAS   |    Akhir    |")
        print("=================================================================================")
        print("|                                TIDAK ADA DATA                                 |")
        print("=================================================================================")
```

```else``` digunakan untuk menampilkan yang terjadi jika Nama yang diketik tidak ada

- Buat program untuk Tambah Data nya

```
def add():
    print("Tambah Data")
    nama = input("Nama\t : ")
    nim = input("NIM\t : ")
    uts = int(input("Nilai UTS\t : "))
    uas = int(input("Nilai UAS\t : "))
    tugas = int(input("Nilai Tugas\t : "))
    akhir = (tugas * 30/100) + (uts * 35/100) + (uas * 35/100)
    mahasiswa[nama] = nim, tugas, uts, uas, akhir
```

- Buat program untuk Hapus data

``` 
def delete():
    print("Hapus Data")
    nama = input("Masukkan Nama : ")
    
    if nama in mahasiswa.keys():
        del mahasiswa[nama]
    
    else:
        print("Nama tidak ditemukan")
```

- Buat program untuk Ubah data 

```
def update():
    print("Ubah Data")
    nama = input("Masukkan Nama : ")
    if nama in mahasiswa.keys():
        nim = input("NIM\t : ")
        uts = int(input("Nilai UTS\t : "))
        uas = int(input("Nilai UAS\t : "))
        tugas = int(input("Nilai Tugas\t : "))
        akhir = (tugas * 30/100) + (uts * 35/100) + (uas * 35/100)
        mahasiswa[nama] = nim, tugas, uts, uas, akhir

    else:
        print("Nama tidak ditemukan ")
```

- Buat program untuk Cari data

```
def search():
    print("Cari Data")
    a = input("Masukkan Nama : ")
    if a in mahasiswa.keys():
        print("===========================================================================")
        print("|      Nama      |     NIM     |  Tugas  |   UTS   |   UAS   |    Akhir   |")
        print("===========================================================================")
        print("| {0:14s} | {1:11s} | {2:7d} | {3:7d} | {4:7d} |     {5:6.2f} |"
            .format (a , mahasiswa[a][0], mahasiswa[a][1], mahasiswa[a][2], mahasiswa[a][3], mahasiswa[a][4] ))
        print("===========================================================================")

    else:
        print("=================================================================================")
        print("| No |      Nama      |     NIM     |  Tugas  |   UTS   |   UAS   |    Akhir    |")
        print("=================================================================================")
        print("|                          DATA TIDAK DITEMUKAN                                 |")
        print("=================================================================================")
```
program ini berbeda dengan melihat data, program ini akan memunculkan nama yang diketik pada input


- Buat program untuk menu nya

``` 
def menu():
    print("\n")
    print("================================")
    print("      Program input nilai       ")
    print("================================\n")

    x = input("[(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar]: ")
    print("\n")

    if x == 'L':
        show()
    elif x == 'T':
        add()
    elif x == 'U':
        update()
    elif x == 'H':
        delete()
    elif x == 'C':
        search()
    elif x == 'K':
        print("==========================================================================")
        print('\n')
        print("> You exit the code                        ")
        print("\n")
        print("==========================================================================")

        exit()

    else:
        print("            KODE YANG ANDA MASUKKAN TIDAK VALID !!!!!!!!!!!")
```

Program berisikan menu, jika ketik L/T/U/H/C/K maka akan menjalankan perintah program program yang diketik di atas seperti ```show()```, ```add()```, ```update()```, ```delete()```, ```search()```

- Kode nya akan berjalan dengan perintah
``` 
while True:
    menu()
```
---
#### Output nya akan menghasilkan:

- Lihat tanpa data

<img width="497" alt="5" src="https://user-images.githubusercontent.com/118233561/203965994-b889f212-1817-4bb9-930e-899065b98af7.png">


- Tambah Data

<img width="359" alt="6" src="https://user-images.githubusercontent.com/118233561/203966057-360247fe-1eb3-475a-9c00-bc9721182f3f.png">


- Lihat dengan data

<img width="511" alt="7" src="https://user-images.githubusercontent.com/118233561/203966081-42e70f5f-afc7-4b71-a0f0-234b8f5a6e9e.png">


- Ubah Data

<img width="368" alt="sut1" src="https://user-images.githubusercontent.com/118233561/203967381-bc31fc0a-7dd2-4752-96f9-0e5b4ad208df.png">


data akan terubah setelah menginputnya

<img width="497" alt="sut2" src="https://user-images.githubusercontent.com/118233561/203967437-33eab9df-2f33-443a-95dd-0638184eb503.png">



- Hapus Data 

<img width="356" alt="8" src="https://user-images.githubusercontent.com/118233561/203967537-85859b6e-f0b3-4899-ae70-bf37050dade4.png">



data akan terhapus

<img width="497" alt="9" src="https://user-images.githubusercontent.com/118233561/203967584-dc158cd3-a2b6-429b-94eb-d2b37fed3b1b.png">


- Cari Data

<img width="500" alt="10" src="https://user-images.githubusercontent.com/118233561/203967647-0ae5d12a-980b-4d2a-a242-05dd567a588a.png">

- Keluar

<img width="462" alt="11" src="https://user-images.githubusercontent.com/118233561/203967679-ca0602ad-d38e-462f-85c8-3e89dcb045a9.png">


- Flowchart

<img width="545" alt="flowchart" src="https://user-images.githubusercontent.com/118233561/203967958-9211a77c-27d0-48a5-9f5f-6e1ab4c4e4ad.png">

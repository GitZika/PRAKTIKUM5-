# PRAKITKUM 5


### Nama:Azhyka Rizki Ramadhan

### NIM:312210287

### Kelas:TI 22 A3

# Latihan 

## Dictionary adalah Koleksi item yang berasosiasi dimana setiap pasangan terdiri _key_ dan _value_.

## _Key_ dan _Value_ sebagai 'Key' : 'Value'

## Dictionary ditulis dengan dipisahkan koma dalam ```{}```

```
telepon = {'Ari' : '081267888', 'Dina' : '087677776'}
```

### untuk menampilkan kontak 
```
print(telepon['Ari'])
```

---

### Untuk menambahkan elemen dictionary 

```
telepon['Riko']
```

---

### untuk mengubah dictionary hampir sama dengan menambahkannya

```
telepon['Dina'] = '088999776'
```

---

### Untuk menampilkan semua nama/key nya menggunakan perintah

```
print(telepon.keys())
```

### Output nya akan menghasilkan

<img width="218" alt="s 1" src="https://user-images.githubusercontent.com/118233561/204115523-552466fb-9937-48cc-aa42-7255cb327384.png">


---

### Untuk menampilkan semua nomor telepon/value

```
print(telepon.values())
```

### Output nya akan menghasilkan 

<img width="321" alt="s 2" src="https://user-images.githubusercontent.com/118233561/204115538-2fcffc83-0e14-4a2d-b66b-ff9c2249d6e5.png">



---

### Untuk menampilkan daftar Nama dan Nomor nya gunakan perintah ```for```

```
for nama,nomor in telepon.items():
    print("%s \t| %s " % (nama,nomor))
```

### Output nya akan menghasilkan

<img width="145" alt="s 3" src="https://user-images.githubusercontent.com/118233561/204115560-7fa0284d-d7e1-4d8d-8b18-428906216fd1.png">


---

### Hapus kontak DIna menggunakan

``` 
del telepon['Dina']
```

### Maka kontak Dina akan terhapus

<img width="150" alt="s 4" src="https://user-images.githubusercontent.com/118233561/204115555-84dd7586-7109-416e-ab28-845cd4230b80.png">


---

# Tugas Praktikum

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

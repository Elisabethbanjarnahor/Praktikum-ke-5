## PROGRAM SEDERHANA YANG DAPAT MENGELOLA DATA NILAI MAHASISWA ##


## ALGORIMANYA ##

ALGORITMA
    inisialisasi daftar_nilai sebagai kamus kosong

    ULANGI
        tampilkan_menu()
        baca pilihan
        SEBARANG pilihan
            KASUS 1: // Tampilkan daftar nilai
                // ... (implementasi seperti di atas)
            KASUS 2: // Tambah data
                // ... (implementasi seperti di atas)
            // ... (kasus untuk opsi lainnya)
        AKHIR SEBARANG
    Hingga pilihan = 'keluar'

## FLOWCHARTNYA ##
![WhatsApp Image 2024-11-23 at 20 15 38_46abe6b1](https://github.com/user-attachments/assets/a635c90d-418d-4263-8504-698c2f786b94)



## CODINGANNYA ##
```ruby
daftar_nilai = {}

def tampilkan_daftar_nilai():
    if not daftar_nilai:
        print("TIDAK ADA DATA")
        return

    print("No\tNIM\tNama\tTugas\tUTS\tUAS\tAkhir")
    for i, (nim, data) in enumerate(daftar_nilai.items(), start=1):
        print(f"{i}\t{nim}\t{data['nama']}\t{data['tugas']}\t{data['UTS']}\t{data['UAS']}\t{data['akhir']}")

def tambah_data():
    nim = input("Masukkan NIM: ")
    nama = input("Masukkan Nama: ")
    tugas = float(input("Masukkan Nilai Tugas: "))
    uts = float(input("Masukkan Nilai UTS: "))
    uas = float(input("Masukkan Nilai UAS: 1  "))
    akhir = (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)
    daftar_nilai[nim] = {"nama": nama, "tugas": tugas, "UTS": uts, "UAS": uas, "akhir": akhir}
    print("Data mahasiswa berhasil ditambahkan.")

def ubah_data():
    nim = input("Masukkan NIM yang ingin diubah: ")
    if nim in daftar_nilai:
        # Minta pengguna memilih data yang ingin diubah
        print(f"Data mahasiswa dengan NIM {nim}:")
        print(daftar_nilai[nim])
        # ... (Implementasi mengubah data)
    else:
        print("NIM tidak ditemukan.")

def hapus_data():
    nim = input("Masukkan NIM yang ingin dihapus: ")
    if nim in daftar_nilai:
        del daftar_nilai[nim]
        print("Data mahasiswa berhasil dihapus.")
    else:
        print("NIM tidak ditemukan.")

def cari_data():
    nim = input("Masukkan NIM yang ingin dicari: ")
    if nim in daftar_nilai:
        print(f"Data mahasiswa dengan NIM {nim}:")
        print(daftar_nilai[nim])
    else:
        print("NIM tidak ditemukan.")

while True:
    print("\nMenu:")
    print("1. Tampilkan Daftar Nilai")
    print("2. Tambah Data")
    print("3. Ubah Data")
    print("4. Hapus Data")
    print("5. Cari Data")
    print("6. Keluar")

    pilihan = input("Pilih menu: ")

    if pilihan == '1':
        tampilkan_daftar_nilai()
    elif pilihan == '2':
        tambah_data()
    elif pilihan == '3':
        ubah_data()
    elif pilihan == '4':
        hapus_data()
    elif pilihan == '5':
        cari_data()
    elif pilihan == '6':
        break
    else:
        print("Pilihan tidak valid.")
```

## PENJELASAN SEDERHANA ##

Cara kerjanya secara garis besar:

1. Membuat Kamus:
= Program memulai dengan membuat sebuah kamus (dictionary) kosong bernama mahasiswa. Kamus ini akan digunakan untuk menyimpan data setiap mahasiswa. Kunci kamus adalah NIM mahasiswa, dan nilainya adalah informasi lain seperti nama, nilai tugas, UTS, UAS, dan nilai akhir.
2. Menu Interaktif:
### Program terus-menerus menampilkan menu pilihan kepada pengguna:
= (L)ihat: Menampilkan semua data mahasiswa dalam bentuk tabel yang rapi.

= (T)ambah: Menambahkan data mahasiswa baru.

= (U)bah: Mengubah data mahasiswa yang sudah ada.

= (H)apus: Menghapus data mahasiswa.

= (C)ari: Mencari data mahasiswa berdasarkan NIM.

= (K)eluar: Keluar dari program.

3 Memilih Aksi:
### Pengguna memilih salah satu opsi dari menu.
### Program akan menjalankan fungsi yang sesuai dengan pilihan pengguna.

=> Secara singkat, program ini memungkinkan pengguna untuk:
Melihat daftar seluruh mahasiswa dan nilai mereka.
Menambahkan data mahasiswa baru.
Mengubah data mahasiswa yang sudah ada.
Menghapus data mahasiswa.
Mencari data mahasiswa berdasarkan NIM.

Dan juga program ini juga menggunakan
Library prettytable:
Library ini digunakan untuk membuat tampilan tabel yang lebih rapi dan mudah dibaca saat menampilkan data mahasiswa.

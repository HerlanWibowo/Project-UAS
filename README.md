## Project-UAS
### Nama :Herlan Wibowo
### NIM  :312210324
### Kelas:TI 22 A3
### Buat program data Mahasiswa Mengggunakan Package dan modul paada Python
#### Saya akan membuat package dan modul di pycharm

![SS1](src/ss1.png)

#### Jika sudah membuat project lalu pilih new dan klik python package untuk membuat package dan modul

![ss2](src/ss2.png)

#### Lalu saya akan membuat modul pada folder modul model dan view

![ss3](src/ss3.png)

#### Membuat kode prodram untuk file daftar_nilai

        kontak = {}


        def tambah_kontak(nama,nim,tugas,uts,uas):
            akhir = round((float(tugas) * 0.3) + (float(uts) * 0.35) + (float(uas) * 0.35), 2)
            kontak[nama] = nama,nim,tugas,uts,uas,akhir


        def ubah_kontak(nama):
            if nama in kontak.keys():
                del kontak[nama]
                print("\n===Masukan Perubahan Data===")
                from view.input_nilai import inputan
                inputan()
            else:
                print(" ________________________")
                print("| Data {} tidak ditemukan |".format(nama))
                print(" ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾")
                print("    (T)Tambah       (U)ubah      (H)Hapus     (C)Cari      (L)Lihat     (K)Keluar   ")


        def cari(nama):
            if nama in kontak.keys():
                print("\n=====================================================================")
                print("|      NAMA       |       NIM        | TUGAS |  UTS  |  UAS  | AKHIR |")
                print("|=================|==================|=======|=======|===============|")
                print("| {0:15} | {1:16} | {2:5} | {3:5} | {4:5} | {5:5} |".format(nama, kontak[nama][1], kontak[nama][2],kontak[nama][3],kontak[nama][4], kontak[nama][5]))
                print("======================================================================")
            else:
                print(" ________________________")
                print("| Data {} tidak ditemukan |".format(nama))
                print(" ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾")


        def hapus(nama):
            if nama in kontak.keys():
                del kontak[nama]
                return True
            else:
                print(" ________________________")
                print("| Data {} tidak ditemukan |".format(nama))
                print(" ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾")
                return False

#### Penjelasan :

    Disini kita menggunakan kamus ya untuk menyimpan inputan data mahasiswa
    Def tambahkan : Dibagian ini kita gunakan print untuk penulisan bagian input data mahasiswa nanti agar terlihat rapih
    Def hapus :
    Disini kita buat inputan yang menginput nama
        Gunanya untuk menghapus data mahasiswa dari nama mahasiswa itu sendiri
        Kita gunakan del untuk fungsi menghapus datanya
        (Jika)Jika mahasiswa tersebut ada maka data mahasiswa tersebut akan terhapus
        (Else)Jika nama mahasiswa tersebut tidak ada maka datanya tidak akan ditemukan
    Def ubah
    Penjelasan:
        Disini kita hampir sama dengan yang hapus, kita gunakan inputan nama untuk mengubah NIM, Nilai Tugas, Ujian Tengah Semester(UTS), ataupun Ujian Akhir Semester(UAS)
        Lalu setelah kita memasukkan nama maka dictionary akan mengeksekusi program menggunakan keys untuk mencari data dari nama mahasiswa tersebut
        (Jika)Jika nama mahasiswa tersebut ketemu atau ada didalam data maka program akan masuk ke inputan NIM, Nilai Tugas, Nilai UTS, dan Nilai UAS yang baru
        (Else)Jika nama mahasiswa tersebut tidak ada didalam data maka program akan memunculkan tulisan atau perintah bahwa data mahasiswa tidak ada
    Def cari
    Penjelasan:
        Fungsinya sama dengan tambahkan Def

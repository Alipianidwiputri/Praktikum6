# Praktikum6

# Coding 1

    kontak = {
    "alpi": "085710092053",
    "sultan": "087815646769"
    }
    print("Kontak alpi:", kontak["alpi"])

    kontak["aldo"] = "082127150958"
    kontak["sultan"] = "087815646769"

    print("Semua Nama:")
    for nama in kontak:
    print(nama)

    print("Semua Nomor:")
    for nomor in kontak.values():
    print(nomor)

    print("Daftar Nama dan Nomornya:")
    for nama, nomor in kontak.items():
    print(nama + ": " + nomor)

    del kontak["sultan"]

    print("Semua Nama:")
    for nama in kontak:
    print(nama)

    print("Semua Nomor:")
    for nomor in kontak.values():
    print(nomor)

    print("Daftar Nama dan Nomornya:")
    for nama, nomor in kontak.items():
     print(nama + ":"+ nomor)

# Hasil Coding 1

![hasil pyhton 1](https://github.com/user-attachments/assets/77bc0bf7-9fba-4d13-8161-b2dabc616774)

# Penjelasan Coding 1

1. Pembuatan Dictionary:

       kontak = {
       "alpi": "085710092053",
       "sultan": "087815646769"
       }

- Ini membuat dictionary bernama kontak yang menyimpan nama sebagai key dan nomor telepon sebagai value
- Awalnya berisi 2 kontak: alpi dan sultan

2. Mengakses Value:

       print("Kontak alpi:", kontak["alpi"])

- Menampilkan nomor telepon alpi dengan mengakses dictionary menggunakan key "alpi"

3. Menambah Data:

       kontak["aldo"] = "082127150958"

- Menambahkan kontak baru dengan nama "aldo" dan nomornya ke dalam dictionary

4. Menampilkan Semua Nama (Keys):

       print("Semua Nama:")
        for nama in kontak:
       print(nama)

- Menggunakan loop untuk menampilkan semua nama (keys) dalam dictionary

5. Menampilkan Semua Nomor (Values):

       print("Semua Nomor:")
         for nomor in kontak.values():
       print(nomor)

- Menggunakan loop dan method .values() untuk menampilkan semua nomor telepon

6. Menampilkan Nama dan Nomor (Key-Value Pairs):

       print("Daftar Nama dan Nomornya:")
       for nama, nomor in kontak.items():
       print(nama + ": " + nomor)

- Menggunakan method .items() untuk mengakses pasangan key-value sekaligus
- Menampilkan nama dan nomor dalam format "nama: nomor"

7. Menghapus Data:

       del kontak["sultan"]

- Menghapus kontak "sultan" dari dictionary menggunakan keyword del

8. Menampilkan Data Setelah Penghapusan:

- Program kemudian mengulangi proses menampilkan nama, nomor, dan pasangan nama-nomor
- Hasilnya menunjukkan bahwa data "sultan" sudah tidak ada dalam dictionary

Dari output yang ditampilkan:

- Awalnya ada 3 kontak (alpi, sultan, aldo)
- Setelah penghapusan tersisa 2 kontak (alpi dan aldo)
- Setiap informasi ditampilkan dengan format yang rapi dan terstruktur

Program ini mendemonstrasikan operasi dasar pada dictionary Python:

- Membuat dictionary
- Mengakses value dengan key
- Menambah data baru
- Menghapus data
- Mengiterasi melalui keys, values, dan items

# Flowchart

![flowchart praktikum6](https://github.com/user-attachments/assets/b5f219f2-03fe-4e4c-9abd-fcae00976b10)

 # coding 2

    # Dictionary untuk menyimpan data mahasiswa
    data_mahasiswa = {}

    # Fungsi untuk menambahkan data mahasiswa
    def tambah_data():
      nim = input("Masukkan NIM: ")
    if nim in data_mahasiswa:
        print("Data dengan NIM ini sudah ada!")
        return
    nama = input("Masukkan Nama: ")
    tugas = float(input("Masukkan Nilai Tugas: "))
    uts = float(input("Masukkan Nilai UTS: "))
    uas = float(input("Masukkan Nilai UAS: "))
    akhir = (0.3 * tugas) + (0.35 * uts) + (0.35 * uas)
    data_mahasiswa[nim] = {"nama": nama, "tugas": tugas, "uts": uts, "uas": uas, "akhir": akhir}
    print("Data berhasil ditambahkan!")

    # Fungsi untuk mengubah data mahasiswa
    def ubah_data():
      nim = input("Masukkan NIM yang ingin diubah: ")
    if nim not in data_mahasiswa:
        print("Data tidak ditemukan!")
        return
    print("Data ditemukan: ", data_mahasiswa[nim])
    nama = input("Masukkan Nama baru: ")
    tugas = float(input("Masukkan Nilai Tugas baru: "))
    uts = float(input("Masukkan Nilai UTS baru: "))
    uas = float(input("Masukkan Nilai UAS baru: "))
    akhir = (0.3 * tugas) + (0.35 * uts) + (0.35 * uas)
    data_mahasiswa[nim] = {"nama": nama, "tugas": tugas, "uts": uts, "uas": uas, "akhir": akhir}
    print("Data berhasil diubah!")

    # Fungsi untuk menghapus data mahasiswa
    def hapus_data():
      nim = input("Masukkan NIM yang ingin dihapus: ")
    if nim in data_mahasiswa:
        del data_mahasiswa[nim]
        print("Data berhasil dihapus!")
    else:
        print("Data tidak ditemukan!")

    # Fungsi untuk mencari data mahasiswa
    def cari_data():
      nim = input("Masukkan NIM yang ingin dicari: ")
    if nim in data_mahasiswa:
        print("Data ditemukan: ", data_mahasiswa[nim])
    else:
        print("Data tidak ditemukan!")

    # Fungsi untuk menampilkan semua data mahasiswa
    def tampilkan_data():
      if not data_mahasiswa:
        print("TIDAK ADA DATA")
        return
    print("Daftar Nilai")
    print("=" * 63)
    print("| NO |    NIM    |      NAMA      | TUGAS | UTS | UAS | AKHIR |")
    print("=" * 63)
    for i, (nim, data) in enumerate(data_mahasiswa.items(), start=1):
        print(f"| {i:<2} | {nim:<9} | {data['nama']:<13} | {data['tugas']:<5} | {data['uts']:<3} | {data['uas']:<3} | {data['akhir']:<5.2f} |")
    print("=" * 63)

    # Program utama
    def main():
      while True:
        print("\n[L]ihat, [T]ambah, [U]bah, [H]apus, [C]ari, [K]eluar")
        pilihan = input("Pilihan: ").lower()
        if pilihan == "l":
            tampilkan_data()
        elif pilihan == "t":
            tambah_data()
        elif pilihan == "u":
            ubah_data()
        elif pilihan == "h":
            hapus_data()
        elif pilihan == "c":
            cari_data()
        elif pilihan == "k":
            print("Keluar dari program. Terima kasih!")
            break
        else:
            print("Pilihan tidak valid!")

    if __name__ == "__main__":
         main()

# hasil Coding 2

![Hasil phyton 2](https://github.com/user-attachments/assets/630b9a64-d5de-49a4-a0e0-f9bba3ccf441)

# Penjelasan 

Berikut adalah ringkasan ulang program manajemen data mahasiswa:  

1.Menu Utama:  
   Program dimulai dengan menampilkan pilihan berikut:  
   - Lihat data mahasiswa: Menampilkan daftar mahasiswa yang ada.  
   - Tambah data mahasiswa: Menambahkan informasi mahasiswa baru.  
   - Ubah data mahasiswa: Memperbarui informasi mahasiswa tertentu.  
   - Hapus data mahasiswa: Menghapus data mahasiswa berdasarkan NIM.  
   - Cari data mahasiswa: Mencari data mahasiswa dengan NIM tertentu.  
   - Keluar: Mengakhiri program.  

2. Lihat Data Mahasiswa:  
   Jika pengguna memilih opsi ini, program akan menampilkan daftar mahasiswa. Jika tidak ada data, program akan menampilkan pesan "TIDAK ADA DATA".  

3. Tambah Data Mahasiswa:  
   - Program meminta pengguna memasukkan NIM.  
   - Jika NIM sudah ada, program akan memberi pesan "DATA SUDAH ADA".  
   - Jika NIM belum ada, program meminta pengguna mengisi data tambahan seperti nama, nilai tugas, nilai UTS, dan nilai UAS.  
   - Program akan menghitung nilai akhir dan menyimpan data tersebut.  

4. Ubah Data Mahasiswa:  
   - Pengguna diminta memasukkan NIM mahasiswa yang ingin diperbarui.  
   - Jika NIM ditemukan, program meminta pengguna mengedit data seperti nama, nilai tugas, nilai UTS, dan nilai UAS.  
   - Program akan menghitung ulang nilai akhir dan menyimpan perubahan.  

5. Hapus Data Mahasiswa:  
   - Pengguna diminta memasukkan NIM mahasiswa yang ingin dihapus.  
   - Jika NIM ditemukan, data akan dihapus dari database.  

6. Cari Data Mahasiswa:  
   - Pengguna diminta memasukkan NIM mahasiswa yang ingin dicari.  
   - Jika NIM ditemukan, program akan menampilkan informasi mahasiswa.  
   - Jika tidak ditemukan, program akan memberi pesan "DATA TIDAK DITEMUKAN".  

7. Keluar:  
   Program akan berhenti ketika opsi ini dipilih.  

Informasi Tambahan:  
- Input NIM: Digunakan untuk memasukkan NIM mahasiswa.  
- Pengecekan Data: Program memastikan apakah NIM sudah ada atau belum.  
- Tampilkan Data: Data mahasiswa akan ditampilkan di layar.  
- Input Informasi Tambahan: Pengguna akan mengisi nama, nilai tugas, nilai UTS, dan nilai UAS.  
- Hitung Nilai Akhir: Program menghitung nilai akhir berdasarkan data yang dimasukkan.  
- Simpan atau Hapus: Data akan disimpan atau dihapus sesuai perintah pengguna.

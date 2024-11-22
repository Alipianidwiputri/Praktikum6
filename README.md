# Praktikum6

# Flowchart

![flowchart praktikum6](https://github.com/user-attachments/assets/b5f219f2-03fe-4e4c-9abd-fcae00976b10)

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

     ![Uploading hasil pyhton 1.png…]()

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


# UAS-Bahasa-Pemrograman
Buatlah program sederhana dengan ketentuan:
• Program harus dibuat dengan konsep modular dan OOP (pisahkan class data, class view, dan class process)
• Program harus meminta input dari pengguna
• Tambahkan validasi input (dapat menggunakan konsep eksepsi)
• Program menapilkan hasil (dapat berupa table view)

![Screenshot 2025-01-04 230555](https://github.com/user-attachments/assets/6034268d-348b-4a05-a5b6-720e76cfb147)
![Screenshot 2025-01-04 230524](https://github.com/user-attachments/assets/981316cc-c428-4831-9469-2d393b2adfd4)

       class Mahasiswa:
    def __init__(self, nama, nim, tugas, uts, uas):
        self.nama = nama
        self.nim = nim
        self.tugas = tugas
        self.uts = uts
        self.uas = uas
        self.nilai_akhir = self.hitung_nilai_akhir()

    def hitung_nilai_akhir(self):
        return (self.tugas * 0.30) + (self.uts * 0.35) + (self.uas * 0.35)

1. Class Mahasiswa
- Tujuan: Menyimpan informasi tentang mahasiswa dan menghitung nilai akhir.
- Atribut:
  - nama: Nama mahasiswa.
  - nim: Nomor Induk Mahasiswa (NIM).
  - tugas: Nilai tugas.
  - uts: Nilai Ujian Tengah Semester (UTS).
  - uas: Nilai Ujian Akhir Semester (UAS).
  - nilai_akhir: Nilai akhir yang dihitung berdasarkan bobot nilai tugas, UTS, dan UAS.
- Metode:
  - __init__: Konstruktor yang menginisialisasi atribut dan menghitung nilai akhir menggunakan metode hitung_nilai_akhir.
  - hitung_nilai_akhir: Menghitung nilai akhir dengan rumus: nilai_akhir=(tugas *0,30 ) + ( uts *0,35 ) + ( uas *0,35 )

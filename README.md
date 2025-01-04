# UAS-Bahasa-Pemrograman
Buatlah program sederhana dengan ketentuan:
• Program harus dibuat dengan konsep modular dan OOP (pisahkan
class data, class view, dan class process)
• Program harus meminta input dari pengguna
• Tambahkan validasi input (dapat menggunakan konsep eksepsi)
• Program menapilkan hasil (dapat berupa table view)


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

    - __init__ Method: Ini adalah konstruktor yang dipanggil saat objek Mahasiswa dibuat. Ia menerima parameter untuk nama, NIM, dan nilai tugas, UTS, dan UAS. Nilai akhir dihitung dengan memanggil metode         
      hitung_nilai_akhir.
    - hitung_nilai_akhir Method: Metode ini menghitung nilai akhir mahasiswa berdasarkan bobot yang telah ditentukan:
    - Tugas: 30%
    - UTS: 35%
    - UAS: 35%

    class ProsesMahasiswa:
    def __init__(self):
        self.mahasiswa_list = []

    def tambah_mahasiswa(self, nama, nim, tugas, uts, uas):
        mahasiswa = Mahasiswa(nama, nim, tugas, uts, uas)
        self.mahasiswa_list.append(mahasiswa)

    def get_mahasiswa(self):
        return self.mahasiswa_list

- __init__ Method: Konstruktor ini menginisialisasi daftar kosong mahasiswa_list untuk menyimpan objek Mahasiswa.
- tambah_mahasiswa Method: Metode ini menerima data mahasiswa, membuat objek Mahasiswa, dan menambahkannya ke dalam mahasiswa_list.
- get_mahasiswa Method: Metode ini mengembalikan daftar mahasiswa yang telah ditambahkan.


    class ViewMahasiswa:
    @staticmethod
    def tampilkan_data(mahasiswa_list):
        print("\nDaftar Nilai Mahasiswa")
        print("=" * 83)
        print("{:<20} {:<15} {:<10} {:<10} {:<10} {:<10}".format(
            "Nama", "NIM", "Tugas", "UTS", "UAS", "Nilai Akhir"))
        print("-" * 83)

        for mhs in mahasiswa_list:
            print("{:<20} {:<15} {:<10} {:<10} {:<10} {:<10.2f}".format(
                mhs.nama,
                mhs.nim,
                mhs.tugas,
                mhs.uts,
                mhs.uas,
                mhs.nilai_akhir
            ))
        print("=" * 83)

- tampilkan_data Method: Metode statis ini menerima daftar mahasiswa dan mencetak data mereka dalam format tabel.
- Menggunakan format untuk memastikan kolom-kolom data teratur dan mudah dibaca.
- Menampilkan nama, NIM, nilai tugas, UTS, UAS, dan nilai akhir.

    def validasi_input(nilai):
    if not isinstance(nilai, (int, float)):
        raise ValueError("Nilai harus berupa angka.")
    if nilai < 0 or nilai > 100:
        raise ValueError("Nilai harus berada dalam rentang 0-100.")


- Fungsi ini memvalidasi input nilai:
- Memastikan nilai adalah angka (int atau float).
- Memastikan nilai berada dalam rentang 0 hingga 100. Jika tidak, akan mengangkat ValueError dengan pesan yang sesuai.

    def main():
    proses = ProsesMahasiswa()
    while True:
        try:
            nama = input("Masukkan Nama: ")
            nim = input("Masukkan NIM: ")
            tugas = float(input("Nilai Tugas: "))
            validasi_input(tugas)
            uts = float(input("Nilai UTS: "))
            validasi_input(uts)
            uas = float(input("Nilai UAS: "))
            validasi_input(uas)

            proses.tambah_mahasiswa(nama, nim, tugas, uts, uas)

            lanjut = input("Tambah data (y/t)? ")
            if lanjut.lower() == 't':
                break
        except ValueError as e:
            print(f"Error: {e}")

    # Tampilkan semua data
    view



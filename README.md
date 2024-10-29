#praktikum
LATIHAN 3:BUAT PROGRAM PYTHON UNTUK KASUS BERIKUT:
KASUS 1:PROGRAM PEMESANAN TIKET BIOSKOP
Buat program yang menghitung harga tiket bioskop.Tiket reguler berharga Rp50.000,
sedangkan tiket VIP berharga Rp100.000.jika user hanya memiliki kartu member,mereka
mendapatkan diskon 20% dari harga tiket.Program ini harus meminta tipe tiket dan status member dari user,lalu menghitung total harga yang harus dibayar.

#Program Phyton menggunakan If else
# Harga tiket
harga_reguler = 50000
harga_vip = 100000
diskon_member = 0.2  # Diskon 20%

# Meminta input dari pengguna
tipe_tiket = input("Masukkan tipe tiket (reguler/VIP): ").strip().lower()
status_member = input("Apakah Anda memiliki kartu member? (ya/tidak): ").strip().lower()

# Menghitung total harga
if tipe_tiket == "reguler":
    total_harga = harga_reguler
elif tipe_tiket == "vip":
    total_harga = harga_vip
else:
    print("Tipe tiket tidak valid.")
    total_harga = None

# Mengecek status member dan menghitung diskon jika berlaku
if total_harga is not None:
    if status_member == "ya":
        total_harga *= (1 - diskon_member)  # Menerapkan diskon
    elif status_member != "tidak":
        print("Status member tidak valid.")
        total_harga = None

# Menampilkan hasil
if total_harga is not None:
    print(f"Total harga yang harus dibayar: Rp{total_harga:.2f}")
    
#Penjelasan
1.Deklarasi Variabel
2.Input pengguna
Program meminta pengguna untuk memasukkan tipe tiket (reguler atau VIP) dan status member (ya atau tidak).
strip() digunakan untuk menghilangkan spasi tambahan, dan lower() memastikan input selalu dalam huruf kecil.
3.Menghitung Total Harga:
Memeriksa tipe tiket yang dimasukkan. Jika valid, harga tiket disimpan di total_harga. Jika tidak valid, menampilkan pesan kesalahan dan mengatur total_harga ke None.
4.Cek Status Member dan Hitung Diskon:
Jika total_harga tidak None, memeriksa status member. Jika member, diskon diterapkan dengan mengalikan total_harga dengan (1 - diskon_member). Jika status member tidak valid, menampilkan pesan kesalahan.
5.menampilkan hasil 
Jika total_harga valid, program mencetak total harga yang harus dibayar dengan format dua desimal.

#Menggunakan operator ternary
# Fungsi untuk menghitung harga tiket
def hitung_harga_tiket(tipe_tiket, status_member):
    harga_reguler = 50000
    harga_vip = 100000

    # Menentukan harga tiket menggunakan operator ternary
    harga = harga_reguler if tipe_tiket.lower() == 'reguler' else harga_vip if tipe_tiket.lower() == 'vip' else None

    if harga is None:
        return "Tipe tiket tidak valid!"

    # Menghitung total harga dengan diskon menggunakan operator ternary
    total_harga = harga * (0.8 if status_member.lower() == 'ya' else 1)
    
    return total_harga

# Meminta input dari user
tipe_tiket = input("Masukkan tipe tiket (reguler/vip): ")
status_member = input("Apakah Anda member? (ya/tidak): ")

# Menghitung total harga dan menampilkan hasil
total = hitung_harga_tiket(tipe_tiket, status_member)
print(f"Total harga yang harus dibayar: Rp{total:.2f}")

#Penjelasan
Operator Ternary: Digunakan untuk menentukan harga tiket dan menghitung total harga.
Untuk harga tiket, jika tipe tiket "reguler", maka harga adalah harga_reguler, jika "vip", maka harga_vip.
Untuk diskon, jika status member "ya", maka harga dikalikan 0.8 (diskon 20%), jika tidak, dikalikan 1.
Input dan Output: Program meminta input dari pengguna untuk tipe tiket dan status member, kemudian menampilkan total harga.

#Kasus 2:Program Kalkulator Sederhana
Buat program kalkulator yang menerima dua angka dan satu operator aritmatika dari pengguna(penjumalahan,pengurangan,perkalian,atau pembagian).program akan menghitung hasil sesuai dengan operator yang dipilih.

#Menggunakan If elif else untuk menentukan operasi aritmatika
# Fungsi kalkulator
def kalkulator(angka1, angka2, operator):
    if operator == '+':
        return angka1 + angka2
    elif operator == '-':
        return angka1 - angka2
    elif operator == '*':
        return angka1 * angka2
    elif operator == '/':
        if angka2 != 0:
            return angka1 / angka2
        else:
            return "Error: Pembagian dengan nol!"
    else:
        return "Error: Operator tidak valid!"

# Meminta input dari pengguna
try:
    angka1 = float(input("Masukkan angka pertama: "))
    angka2 = float(input("Masukkan angka kedua: "))
    operator = input("Masukkan operator (+, -, *, /): ")

    # Menghitung dan menampilkan hasil
    hasil = kalkulator(angka1, angka2, operator)
    print(f"Hasil: {hasil}")
except ValueError:
    print("Error: Input harus berupa angka!")
    
#Penejelasan:
Cara Kerja Program:
1.Fungsi Kalkulator: Menerima dua angka dan satu operator. Berdasarkan operator yang dipilih, fungsi menghitung hasilnya.
2.Input Pengguna: Program meminta pengguna untuk memasukkan dua angka dan operator.
3.Error Handling: Menggunakan try untuk menangkap kesalahan jika pengguna memasukkan nilai yang tidak valid (bukan angka).
4.Menampilkan Hasil: Hasil dari operasi ditampilkan. Jika terjadi pembagian dengan nol atau operator tidak valid, pesan kesalahan ditampilkan.

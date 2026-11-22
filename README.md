# projectalgo
def main():
    siapkan_database()
    while True:
        judul("ENAAKIN RESTORAN")
        print("1. Masuk sebagai Pelanggan\n2. Masuk sebagai Admin")
        print("3. Registrasi Pelanggan\n0. Keluar")
        pilih = input("Pilih: ").strip()
        if pilih in ("1", "2"):
            peran = "pelanggan" if pilih == "1" else "admin"
            user = login(peran)
            if user:
                enter()
                (menu_admin if peran == "admin" else menu_pelanggan)(user)
            else:
                enter()
        elif pilih == "3":
            registrasi()
            enter()
        elif pilih == "0":
            print("Terima kasih telah menggunakan Enaakin Restoran!")
            break
        else:
            print("Pilihan tidak valid.")

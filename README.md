# asd-post-test-3
class Perpustakaan:
    KodeNovel = ...
    Judul = ...

pilih = 0
DataNovel = []

def menu():
    print("=========================================")
    print("|        MENU PERPUSTAKAAN NOVEL        |")
    print("=========================================")
    print("|        1. Input Data Novel Baru       |")
    print("|   2. Tampilkan Novel Yang Tresedia    |")
    print("|         3. Update Data Novel          |")
    print("|         4. Keluar Dari Menu           |")
    print("=========================================")
    pilih = int(input("Masukkan Pilihan Anda : "))
    if pilih == 1:
        pilih1()
        menu()
    elif pilih == 2:
        tampil()
        input("Kembali Ke Menu Utama")
        menu()
    elif pilih == 3:
        index_update = -1
        tampil()
        id_edit = int(input("Input Kode Novel Yang Akan DI Update "))
        for a in range(0, len(DataNovel)):
            if id_edit == DataNovel[a].KodeNovel:
                index_update = a
                break
        if (index_update > -1):
            print("Input Data Yang Di Update ")
            Novel = Perpustakaan()
            Novel.KodeNovel = (int(input("Masukkan Kode Novel : ")))
            Novel.Judul = (input("Masukkan Judul Novel : "))
            DataNovel[index_update] = Novel
            print("Berhasil Update Data Novel")
            print("==========================")
        else:
            print("Kode Novel Tidak Ditemukan")
        input("Kembali Ke Menu Utama ")
        menu()
    elif pilih == 4:
        print("=========================================")
        print("|          PERPUSTAKAAN NOVEL           |")
        print("|     TERIMA KASIH TELAH BERKUNJUNG     |")
        print("=========================================")
        exit()

def tampil():
    print("=========================================")
    print("               DATA NOVEL                ")
    print("=========================================")
    for data in DataNovel:
        print("KodeNovel : " + str(data.KodeNovel))
        print("Judul : " + data.Judul)
        print("-----------------------------------------")

def pilih1():
    ulang = 'Y'
    while ulang in ('y', 'Y'):
        NovelBaru = Perpustakaan()
        print("Input Data Novel Baru")
        NovelBaru.KodeNovel = (int(input("Masukkan Kode Novel : ")))
        NovelBaru.Judul = (input("Masukkan Judul Novel Baru : "))
        DataNovel.append(NovelBaru)
        ulang = input("Apakah Anda Ingin Menambah Novel Baru (Y/T)? ")

menu()

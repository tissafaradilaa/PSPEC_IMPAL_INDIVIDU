# 📚 Program Manajemen Data Anggota Perpustakaan

Program dibuat menggunakan bahasa C untuk mengelola data anggota perpustakaan, meliputi fitur:
1. Menambah anggota baru
2. Menampilkan semua anggota
3. Mengedit data anggota
4. Menghapus anggota
5. Mencetak daftar anggota

Program memakai struktur struct C untuk mendefinisikan data anggota:
typedef struct {
    char id_anggota[10];
    char nama[50];
    char jekel[10];
    char kelas[10];
    char no_hp[15];
} Anggota;

Semua data anggota disimpan di array Anggota anggota[MAX_ANGGOTA], dengan maksimum 100 anggota.

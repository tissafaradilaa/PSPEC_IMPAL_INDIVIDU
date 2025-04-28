#include <stdio.h>
#include <string.h>

#define MAX_ANGGOTA 100

typedef struct {
    char id_anggota[10];
    char nama[50];
    char jekel[10];
    char kelas[10];
    char no_hp[15];
} Anggota;

Anggota anggota[MAX_ANGGOTA];
int jumlah_anggota = 0;

// Fungsi untuk menambahkan anggota
void tambah_anggota() {
    if (jumlah_anggota >= MAX_ANGGOTA) {
        printf("Kapasitas anggota penuh!\n");
        return;
    }
    
    Anggota a;
    sprintf(a.id_anggota, "A%03d", jumlah_anggota + 1);  // Buat ID otomatis
    
    printf("Nama: ");
    scanf(" %[^\n]", a.nama);
    printf("Jenis Kelamin (Laki-laki/Perempuan): ");
    scanf(" %[^\n]", a.jekel);
    printf("Kelas: ");
    scanf(" %[^\n]", a.kelas);
    printf("No HP: ");
    scanf(" %[^\n]", a.no_hp);

    anggota[jumlah_anggota] = a;
    jumlah_anggota++;

    printf("Anggota berhasil ditambahkan!\n");
}

// Fungsi untuk menampilkan semua anggota
void tampilkan_semua_anggota() {
    if (jumlah_anggota == 0) {
        printf("Tidak ada data anggota.\n");
        return;
    }
    
    printf("\nData Anggota:\n");
    printf("No\tID Anggota\tNama\t\tJK\tKelas\tNo HP\n");
    for (int i = 0; i < jumlah_anggota; i++) {
        printf("%d\t%s\t\t%s\t%s\t%s\t%s\n", 
            i + 1, 
            anggota[i].id_anggota, 
            anggota[i].nama, 
            anggota[i].jekel, 
            anggota[i].kelas, 
            anggota[i].no_hp
        );
    }
}

// Fungsi untuk mengedit anggota
void edit_anggota() {
    char id[10];
    printf("Masukkan ID anggota yang ingin diedit: ");
    scanf(" %[^\n]", id);

    int found = 0;
    for (int i = 0; i < jumlah_anggota; i++) {
        if (strcmp(anggota[i].id_anggota, id) == 0) {
            found = 1;
            printf("Mengedit anggota dengan ID: %s\n", id);
            printf("Nama baru: ");
            scanf(" %[^\n]", anggota[i].nama);
            printf("Jenis Kelamin baru: ");
            scanf(" %[^\n]", anggota[i].jekel);
            printf("Kelas baru: ");
            scanf(" %[^\n]", anggota[i].kelas);
            printf("No HP baru: ");
            scanf(" %[^\n]", anggota[i].no_hp);
            printf("Data anggota berhasil diperbarui!\n");
            break;
        }
    }
    if (!found) {
        printf("Anggota dengan ID %s tidak ditemukan!\n", id);
    }
}

// Fungsi untuk menghapus anggota
void hapus_anggota() {
    char id[10];
    printf("Masukkan ID anggota yang ingin dihapus: ");
    scanf(" %[^\n]", id);

    int found = 0;
    for (int i = 0; i < jumlah_anggota; i++) {
        if (strcmp(anggota[i].id_anggota, id) == 0) {
            found = 1;
            for (int j = i; j < jumlah_anggota - 1; j++) {
                anggota[j] = anggota[j + 1];  // Geser elemen array ke kiri
            }
            jumlah_anggota--;
            printf("Anggota dengan ID %s berhasil dihapus!\n", id);
            break;
        }
    }
    if (!found) {
        printf("Anggota dengan ID %s tidak ditemukan!\n", id);
    }
}

// Fungsi untuk mencetak semua data anggota
void print_semua_anggota() {
    if (jumlah_anggota == 0) {
        printf("Tidak ada data anggota untuk dicetak.\n");
        return;
    }

    printf("\nMencetak semua data anggota:\n");
    for (int i = 0; i < jumlah_anggota; i++) {
        printf("ID Anggota: %s\n", anggota[i].id_anggota);
        printf("Nama: %s\n", anggota[i].nama);
        printf("Jenis Kelamin: %s\n", anggota[i].jekel);
        printf("Kelas: %s\n", anggota[i].kelas);
        printf("No HP: %s\n\n", anggota[i].no_hp);
    }
}

int main() {
    int pilihan;
    do {
        printf("\n=== Menu Sistem Perpustakaan ===\n");
        printf("1. Tambah Anggota\n");
        printf("2. Tampilkan Semua Anggota\n");
        printf("3. Edit Anggota\n");
        printf("4. Hapus Anggota\n");
        printf("5. Print Semua Anggota\n");
        printf("0. Keluar\n");
        printf("Pilih menu: ");
        scanf("%d", &pilihan);

        switch (pilihan) {
            case 1:
                tambah_anggota();
                break;
            case 2:
                tampilkan_semua_anggota();
                break;
            case 3:
                edit_anggota();
                break;
            case 4:
                hapus_anggota();
                break;
            case 5:
                print_semua_anggota();
                break;
            case 0:
                printf("Keluar dari program.\n");
                break;
            default:
                printf("Pilihan tidak valid!\n");
        }
    } while (pilihan != 0);

    return 0;
}

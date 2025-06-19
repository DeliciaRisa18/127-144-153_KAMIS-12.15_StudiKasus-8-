# 127-144-153_KAMIS-12.15_StudiKasus-8-

#include <iostream>
#include <iomanip>
#include <vector>
#include <string>

using namespace std;

int main() {
    int jumlahHari, jumlahProduk;

    cout << "\n\t\t======================================" << endl;
    cout << "\t\t|         TOKO PAK ANDI              |" << endl;
    cout << "\t\t======================================" << endl;

    cout << "\nMasukkan jumlah maksimum hari : ";
    cin >> jumlahHari;
    cout << "Masukkan jumlah maksimum produk : ";
    cin >> jumlahProduk;

    vector<string> namaProduk(jumlahProduk);
    vector<vector<int>> penjualan(jumlahHari, vector<int>(jumlahProduk));
    int totalKeseluruhan = 0;

    for (int i = 0; i < jumlahProduk; ++i) {
        cout << "Masukkan nama produk ke-" << i + 1 << " : ";
        cin >> ws;
        getline(cin, namaProduk[i]);
    }

    for (int h = 0; h < jumlahHari; ++h) {
        cout << "\nMasukkan penjualan untuk hari " << h + 1 << endl;
        for (int p = 0; p < jumlahProduk; ++p) {
            cout << "jumlah penjualan " << namaProduk[p] << " : ";
            cin >> penjualan[h][p];
            totalKeseluruhan += penjualan[h][p];
        }
    }

    cout << "\n\t\t======================================" << endl;
    cout << "\t\t|    Data penjualan Toko Pak Andi    |" << endl;
    cout << "\t\t======================================" << endl;

    cout << "\t\t| Hari ";
    for (int i = 0; i < jumlahProduk; ++i) {
        cout << "| " << setw(8) << left << namaProduk[i];
    }
    cout << "|\n";

    cout << "\t\t======================================";
    for (int i = 1; i < jumlahProduk; ++i) cout << "==========";
    cout << endl;

    for (int h = 0; h < jumlahHari; ++h) {
        cout << "\t\t| Hari " << h + 1 << " |";
        for (int p = 0; p < jumlahProduk; ++p) {
            cout << " " << setw(6) << penjualan[h][p] << " |";
        }
        cout << endl;
    }

    cout << "\n\t\t======================================" << endl;
    cout << "\t\t| Total penjualan : " << setw(8) << totalKeseluruhan << " |" << endl;
    cout << "\t\t======================================" << endl;

    return 0;
}

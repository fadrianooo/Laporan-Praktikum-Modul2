# <h1 align="center">Laporan Praktikum Modul 2 Struktur Data </h1>
<p align="center">Fadriano Bumindra Abiyyu - 109082500170</p>

## Dasar Teori
### A. Array <br/>
Array adalah tipe data terstruktur yang menyimpan banyak data bertipe sama dengan satu nama, menempati memori secara berurutan, dan diakses lewat indeks yang dimulai dari 0[1].
#### 1. Array Satu Dimensi
Array satu dimensi adalah array yang hanya terdiri dari satu baris data[3].
#### 2. Array Dua Dimensi
Array dua dimensi adalah array dengan indeks, baris dan kolom, digunakan untuk menyimpan data berbentuk matriks atau tabel[1].
### B. Pointer <br/>
Pointer adalah variabel yang berisi alamat memori dari variabel lain[1][3].
#### 1. Pointer dan Alamat
Operator & digunakan untuk mengambil alamat variabel, dan operator * untuk mengakses nilai yang ditunjuk pointer[3].
#### 2. Pointer dan Array
Elemen array disimpan berurutan di memori, sehingga array dapat diakses menggunakan pointer[3]. 

## Guided 

### Array 1. 

```C++
#include <iostream>
using namespace std;

int main() {
    int nilai[5];

    nilai[0] = 80;
    nilai[1] = 85;
    nilai[2] = 90;
    nilai[3] = 75;
    nilai[4] = 95;

    for (int i = 0; i < 5; i++) {
        cout << "index ke-" << i << " = " << nilai[i] << endl;
    }

    return 0;
}
```
Program ini membuat array satu dimensi bernama nilai bertipe int dengan 5 elemen. Setiap elemen diisi nilai secara langsung lewat indeksnya, indeks array dimulai dari 0. Lalu perulangan menampilkan setiap elemen beserta indeksnya, dari indeks 0 sampai 4.

### Array 2. 

```C++
#include <iostream>
using namespace std;

int main() {
    int nilai[3][3] = {
        {80, 85, 90},
        {75, 80, 85},
        {90, 95, 100}
    };

    cout << nilai[0][0] << endl; // 80
    cout << nilai[1][1] << endl; // 80
    cout << nilai[2][2] << " " ; // 100

    return 0;
}
```
Program ini membuat array dua dimensi, yaitu tabel dengan 3 baris dan 3 kolom. Elemen diakses dengan dua indeks, yaitu baris pertama kolom pertama, baris kedua kolom kedua, dan baris ketiga kolom ketiga. Indeks baris dan kolom sama sama dimulai dari 0.

### Array 3. 

```C++
#include <iostream>
using namespace std;

int main() {
    int data[2][3][3] = {
        {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        },
        {
            {10, 11, 12},
            {13, 14, 15},
            {16, 17, 18}
        }
    };

    cout << data[0][1][1] << " "; // 5

    return 0;
}
```
Program ini membuat array tiga dimensi, yaitu 2 blok yang masing masing berisi tabel 3 baris dan 3 kolom. Elemen diakses dengan tiga indeks, yaitu blok, baris, lalu kolom. Array ini deklarasinya sama dengan dua dimensi, hanya ditambah satu indeks lagi, dan indeks dimulai dari 0.

### Array 4. 

```C++
#include <iostream>
using namespace std;

int main() {
    int data[2][2][2][2] = {
        {
            {
                {1, 2},
                {3, 4}
            },
            {
                {5, 6},
                {7, 8}
            }
        },
        {
            {
                {9, 10},
                {11, 12}
            },
            {
                {13, 14},
                {15, 16}
            }
        }
    };

    cout << data[0][0][0][0] << endl; // 1
    cout << data[1][1][1][1] << endl; // 16

    return 0;
}
```
Program ini membuat array empat dimensi dengan total 16 elemen (2 x 2 x 2 x 2). Elemen diakses dengan empat indeks, dan semua indeks dimulai dari 0.

### Pointer 1. 

```C++
#include <iostream>
using namespace std;

int main() {
    char a;
    int j;
    char arr[6];

    arr[3] = 'b';
    a = 'u';
    j = 10;

    cout << a << endl;   // u
    cout << &a << endl;  // alamat memory atau address

    cout << j << endl;   // 10
    cout << &j << endl;  // alamat memory atau address

    cout << arr[3] << endl;    // value
    cout << &(arr[4]) << endl; // alamat memory atau address

    return 0;
}
```
Program ini menampilkan nilai dan alamat memori dari variabel. Variabel a, j, dan array arr disimpan di lokasi memori masing-masing. Nilai variabel ditampilkan langsung (a, j, arr[3]), sedangkan alamatnya diambil dengan operator & (&a, &j, &arr[4]).

### Pointer 2. 

```C++
#include <iostream>
using namespace std;

int main() {
    int x, y;
    int *px;

    x = 87;
    px = &x;
    y = *px;

    cout << "Alamat x= " << &x << endl;
    cout << "Isi px= " << px << endl;
    cout << "Isi X= " << x << endl;
    cout << "Nilai yang ditunjuk px= " << *px << endl;
    cout << "Nilai y= " << y << endl;

    return 0;
}
```
Program ini menunjukkan cara kerja pointer. Variabel px dideklarasikan sebagai pointer ke int, lalu diisi alamat x lewat px = &x;, sehingga px menunjuk ke x. Operator * pada *px mengambil nilai yang ditunjuk pointer, yaitu 87, dan nilainya disalin ke y. Pada output, alamat x dan isi px bernilai sama, karena px memang menyimpan alamat x. Nilai x, *px, dan y semuanya 87.

### Pointer 3. 

```C++
#include <iostream>
#define MAX 5
using namespace std;

int main() {
    int i, j;
    float nilai_total, rata_rata;
    float nilai[MAX];

    static int nilai_tahun[MAX][MAX] = {
        {0, 2, 2, 0, 0},
        {0, 1, 1, 1, 0},
        {0, 3, 3, 3, 0},
        {4, 4, 0, 0, 4},
        {5, 0, 0, 0, 5}
    };

    // inisialisasi array satu dimensi
    for (i = 0; i < MAX; i++) {
        cout << "masukkan nilai ke-" << i + 1 << endl;
        cin >> nilai[i];
    }

    cout << "\ndata nilai siswa :\n";

    // menampilkan array satu dimensi
    for (i = 0; i < MAX; i++) {
        cout << "nilai k-" << i + 1 << "=" << nilai[i] << endl;
    }

    cout << "\nnilai tahunan :\n";

    // menampilkan array dua dimensi
    for (i = 0; i < MAX; i++) {
        for (j = 0; j < MAX; j++) {
            cout << nilai_tahun[i][j];
        }
        cout << "\n";
    }

    return 0;
}
```
Program ini memakai array satu dimensi nilai yang diisi dari keyboard dan ditampilkan dengan perulangan for, serta array dua dimensi nilai_tahun yang ditampilkan dengan dua perulangan bersarang (baris dan kolom).

### Pointer 4. 

```C++
#include <iostream>
using namespace std;

int main() {
    char nama[] = "strukdat";

    cout << nama << endl;
    cout << nama[3] << endl;

    return 0;
}
```
Program ini membuat string nama berisi "strukdat" menggunakan array karakter (char). String ditampilkan langsung dengan cout << nama, sedangkan satu karakternya diakses lewat indeks seperti array, sehingga nama[3] menampilkan karakter ke-4, yaitu u, karena indeks dimulai dari 0.

## Unguided 

### 1. Buatlah program yang dapat melakukan operasi penjumlahan, pengurangan, dan perkalian matriks 3x3.

```C++
#include <iostream>
using namespace std;

int main() {
    int A[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    int B[3][3] = {
        {9, 8, 7},
        {6, 5, 4},
        {3, 2, 1}
    };

    int C[3][3];

    cout << "\n1. Penjumlahan (A + B):" << endl;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            C[i][j] = A[i][j] + B[i][j];
            cout << C[i][j] << "\t";
        }
        cout << endl;
    }
    cout << "\n2. Pengurangan (A - B):" << endl;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            C[i][j] = A[i][j] - B[i][j];
            cout << C[i][j] << "\t";
        }
        cout << endl;
    }
    cout << "\n3. Perkalian (A * B):" << endl;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            C[i][j] = 0;
            for (int k = 0; k < 3; k++) {
                C[i][j] += A[i][k] * B[k][j];
            }
            cout << C[i][j] << "\t";
        }
        cout << endl;
    }

    return 0;
}
```
### Output Unguided 1 :
Penjumlahan (A + B):
10      10      10
10      10      10
10      10      10

Pengurangan (A - B):
-8      -6      -4
-2      0       2
4       6       8

Perkalian (A * B):
30      24      18
84      69      54
138     114     90

##### Output
![Screenshot Output Unguided 1_1](https://github.com/fadrianooo/Laporan-Praktikum-Modul2/blob/main/Laprak-Modul2/Output-Unguided/Output-Unguided-Modul2-1_1.png)

Program ini melakukan operasi penjumlahan, pengurangan, dan perkalian pada dua matriks 3x3 menggunakan array dua dimensi dan perulangan bersarang, lalu menampilkan hasilnya dalam bentuk matriks.

### 2. Berdasarkan guided pointer dan reference sebelumnya, buatlah keduanya dapat menukar nilai dari 3 variabel.

```C++
#include <iostream>
using namespace std;
void tukarPointer(int *x, int *y, int *z) {
    int temp = *x;
    *x = *y;
    *y = *z;
    *z = temp;
}
void tukarReference(int &x, int &y, int &z) {
    int temp = x;
    x = y;
    y = z;
    z = temp;
}
int main() {
    int a, b, c;
    cout << "nilai a : "; cin >> a;
    cout << "nilai b : "; cin >> b;
    cout << "nilai c : "; cin >> c;

    cout << "\nNilai awal : a = " << a << ", b = " << b << ", c = " << c << endl;

    tukarPointer(&a, &b, &c);
    cout << "Setelah tukar pointer : a = " << a << ", b = " << b << ", c = " << c << endl;

    tukarReference(a, b, c);
    cout << "Setelah tukar reference : a = " << a << ", b = " << b << ", c = " << c << endl;

    return 0;
}
```
### Output Unguided 2 :
nilai a : 10
nilai b : 20
nilai c : 30

Nilai awal : a = 10, b = 20, c = 30
Setelah tukar pointer : a = 20, b = 30, c = 10
Setelah tukar reference : a = 30, b = 10, c = 20
##### Output
![Screenshot Output Unguided 2_1](https://github.com/fadrianooo/Laporan-Praktikum-Modul2/blob/main/Laprak-Modul2/Output-Unguided/Output-Unguided-Modul2-2_1.png)

Program ini menukar nilai tiga variabel dengan dua cara yaitu pointer (tukarPointer) dan reference (tukarReference), sehingga nilai variabel asli ikut berubah.

### 3. Diketahui sebuah array 1 dimensi sebagai berikut :
arrA = {11, 8, 5, 7, 12, 26, 3, 54, 33, 55}
Buatlah program yang dapat mencari nilai minimum, maksimum, dan rata – rata dari
array tersebut! Gunakan function cariMinimum() untuk mencari nilai minimum dan
function cariMaksimum() untuk mencari nilai maksimum, serta gunakan prosedur
hitungRataRata() untuk menghitung nilai rata – rata! Buat program menggunakan
menu switch-case seperti berikut ini :
--- Menu Program Array ---
1. Tampilkan isi array
2. cari nilai maksimum
3. cari nilai minimum
4. Hitung nilai rata - rata

```C++
#include <iostream>
using namespace std;

const int PANJANG = 10;
int cariMinimum(int arr[], int n) {
    int min = arr[0];
    for (int i = 1; i < n; i++)
        if (arr[i] < min)
            min = arr[i];
    return min;
}
int cariMaksimum(int arr[], int n) {
    int max = arr[0];
    for (int i = 1; i < n; i++)
        if (arr[i] > max)
            max = arr[i];
    return max;
}
void hitungRataRata(int arr[], int n) {
    int total = 0;
    for (int i = 0; i < n; i++)
        total += arr[i];
    float rata = (float) total / n;
    cout << "Nilai rata-rata: " << rata << endl;
}

int main() {
    int arrA[PANJANG] = {11, 8, 5, 7, 12, 26, 3, 54, 33, 55};
    int pilihan;

    do {
        cout << "\n--- Menu Program Array ---" << endl;
        cout << "1. Tampilkan isi array" << endl;
        cout << "2. Cari nilai maksimum" << endl;
        cout << "3. Cari nilai minimum" << endl;
        cout << "4. Hitung nilai rata - rata" << endl;
        cout << "Pilih menu: ";
        cin >> pilihan;

        switch (pilihan) {
            case 1:
                cout << "Isi array: ";
                for (int i = 0; i < PANJANG; i++)
                    cout << arrA[i] << " ";
                cout << endl;
                break;
            case 2:
                cout << "Nilai maksimum: " << cariMaksimum(arrA, PANJANG) << endl;
                break;
            case 3:
                cout << "Nilai minimum: " << cariMinimum(arrA, PANJANG) << endl;
                break;
            case 4:
                hitungRataRata(arrA, PANJANG);
                break;
            default:
                cout << "Pilihan tidak valid! Program selesai." << endl;
        }
    } while (pilihan >= 1 && pilihan <= 4);

    return 0;
}
```
### Output Unguided 3 :
--- Menu Program Array ---
1. Tampilkan isi array
2. Cari nilai maksimum
3. Cari nilai minimum
4. Hitung nilai rata - rata
Pilih menu: 1
Isi array: 11 8 5 7 12 26 3 54 33 55 

--- Menu Program Array ---
1. Tampilkan isi array
2. Cari nilai maksimum
3. Cari nilai minimum
4. Hitung nilai rata - rata
Pilih menu: 2
Nilai maksimum: 55

--- Menu Program Array ---
1. Tampilkan isi array
2. Cari nilai maksimum
3. Cari nilai minimum
4. Hitung nilai rata - rata
Pilih menu: 3
Nilai minimum: 3

--- Menu Program Array ---
1. Tampilkan isi array
2. Cari nilai maksimum
3. Cari nilai minimum
4. Hitung nilai rata - rata
Pilih menu: 4
Nilai rata-rata: 21.4
##### Output 1
![Screenshot Output Unguided 3_1](https://github.com/fadrianooo/Laporan-Praktikum-Modul2/blob/main/Laprak-Modul2/Output-Unguided/Output-unguided-Modul2-3_1.png)

Program ini memakai array satu dimensi (arrA) berisi 10 angka yang diakses lewat satu indeks (0-9). Menu ditampilkan berulang dengan do while dan diproses lewat switch: isi array ditampilkan dengan for, nilai maksimum (55) dan minimum (3) dicari dengan membandingkan elemen satu per satu terhadap nilai acuan, dan rata-rata dihitung dari total 214 dibagi 10 (hasil 21). Program berhenti saat pengguna memasukkan angka di luar 1-4.

## Kesimpulan
Array dapat dipakai untuk menyimpan dan mengolah banyak data bertipe sama, termasuk matriks 3x3. Pointer menyimpan alamat variabel, dan call by pointer maupun call by reference membuat fungsi dapat mengubah variabel asli, berbeda dengan call by value yang hanya mengubah salinan. Pemisahan program menjadi fungsi dan prosedur membuat kode lebih terstruktur.

## Referensi
[1] Setiyawan, R. D., Hermawan, D., Abdillah, A. F., Mujayanah, A., & Vindua, R. (2024). "Penggunaan Struktur Data Stack dalam Pemrograman C++ dengan Pendekatan Array dan Linked List". JUTECH (Jurnal Teknologi), Vol. 5, No. 2, Desember 2024, hlm. 484-498. Diakses pada 5 Oktober 2026 melalui https://jurnal.stkippersada.ac.id/jurnal/index.php/jutech/article/download/4263/pdf. <br>
[2] Azzahrani, N. N., & Susanti, D. R. (2025). "Perancangan dan Implementasi Program Penjualan Produk Matcha Menggunakan Bahasa Pemrograman C++ pada Matchuchu Griya". Jukompak (Jurnal Komputasi dan Pengembangan Aplikasi), Vol. 1, No. 4, Oktober 2025, hlm. 11-21. Diakses pada 5 Oktober 2026 melalui https://journals.arces.org/jukompak/article/download/186/112. <br>
[3] Fakultas Informatika, Telkom University. (n.d.). "Modul 2: Pengenalan Bahasa C++ (Bagian Kedua)". Modul Praktikum Struktur Data. Informatics Lab.

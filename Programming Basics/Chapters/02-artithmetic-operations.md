# Arithmetic Operations

Ada beberapa operasi aritmatika yang dapat dilakukan dalam C++

    Simbol  |  Nama Operasi
  --------- | -----------
      +     |  Penjumlahan
      -     |  Pengurangan
      *     |  Perkalian  
      /		|  Pembagian
      %     |  Modulus

Contoh pengunaan operasi aritmatika pada C++ :  

```cpp
#include <iostream>

using namespace std;

int main() {
    cout << "Penjumlahan  4 + 5 = " << 4 + 5 << endl;
    cout << "Pengurangan  4 - 5 = " << 4 - 5 << endl;
    cout << "Perkalian    4 * 5 = " << 4 * 5 << endl;
    cout << "Pembagian    4 / 5 = " << 4 / 5 << endl;
    cout << "Modulus dari 4 % 5 = " << 4 % 5 << endl;
    
    return 0;
}
```

Hasil Output :
```
Penjumlahan  4 + 5 = 9
Pengurangan  4 - 5 = -1
Perkalian    4 * 5 = 20
Pembagian    4 / 5 = 0
Modulus dari 4 % 5 = 4
```

# Cara kerja Operasi Pembagian dan Modulus

### 1. Operasi Pembagian dalam C++
Dalam C++, Operasi Pembagian sedikit berbeda daripada pembagian matematika biasanya.
Contohnya, jika anda perhatikan, Hasil pembagian `4 / 5` hasilnya adalah `0`.

Alasan mengapa hasil pembagian tersebut adalah `0`, karena Compiler C++ mengklasifikasikan pembagian tersebut sebagai pembagian `integer` atau disebut juga pembagian bernilai bulat.

Yang dilakukan oleh program ketika melakukan operasi bilangan bulat adalah 

`4 / 5` --dihitung--> `0.8` ---dibulatkan kebawah---> `0`

##### Cara Alternatif untuk pembagian

Seringkali, keinginan untuk dibulatkan ini dibutuhkan dalam beberapa algoritma terkenal. Namun, untuk kasus ini, fitur ini tidak ingin digunakan.

Untuk menghindari pembagian seperti ini, kita dapat memberitahu compiler lebih dahulu bahwa pembagian yg kita inginkan bukan pembagian bilangan bulat, tetapi bilangan real.

Caranya adalah cukup dengan menambahkan `.0` atau `.f` dibelakangnya

```cpp
    cout << "Pembagian 4 / 5 = " << 4.0 / 5.0 << endl;
```

Hasilnya :

```
Pembagian 4 / 5 = 0.8
```

Dengan menambahkan `.0` atau `.f` kita dapat memberitahu compiler bahwa nilai tersebut bukanlah bilangan bulat, tetapi bilangan real.

Compiler akan selalu melakukan operasi pembagian bilangan real jika salah satu nilai dari operasi tersebut adalah bilangan real.

Contoh :

```cpp
#include <iostream>

using namespace std;

int main() {
    cout << "Pembagian 4.f / 5.f = " << 4.f / 5.f << endl;
    cout << "Pembagian 4   / 5.f = " << 4   / 5.f << endl;
    cout << "Pembagian 4.f / 5   = " << 4.f / 5   << endl;
    cout << "Pembagian 4   / 5   = " << 4   / 5   << endl;
    
    return 0;
}
```

Hasilnya :

```
Pembagian 4.f / 5.f = 0.8
Pembagian 4   / 5.f = 0.8
Pembagian 4.f / 5   = 0.8
Pembagian 4   / 5   = 0
```

### 2. Operasi Modulus

Cara kerja operasi modulus pada C++ adalah seperti perarahan Jarum jam. Untuk memudahkan memahaminya, kita akan menggunakan pertanyaan tentang waktu.

Bayangkan ada sebuah jam dinding analog yang mempunya angka dari 1 - 12.

- Jam tersebut sekarang dalam posisi 4:00. Jika jam tersebutnya dimajukan 5 jam, maka yang terlihat pada jam tersebut adalaha 9:00.

- Pada saat jam tersebut pada posisi Jam 11:00 dan dimajukan 3 jam, maka yang terlihat pada jam tersebut adalah 2:00.

- Pada posisi Jam 8:00 dan dimajukan 24 jam, maka yang terlihat pada jam tersebut adalah jam 8:00.

Cara kerja operasi modulus sama seperti cara kerja perputaran arah jarum jam, hanya saja, angka 12 nya ditulis sebagai 0. Pada contoh sebelumnya, permasalahan tersebut dapat dituliskan dalam bentuk matematika.

- ( 4 +  5) % 12 =  9 % 12 = 9
- (11 +  3) % 12 = 14 % 12 = 2
- ( 8 + 24) % 12 = 32 % 12 = 8

cara mudah untuk menghitung operasi modulus adalah dengan melakukan pembagian biasa, dan nilai yang diambil adalah nilai hasil baginya, contoh :

32 % 12 = ?

```
       2
    /--------
12 /  32
      24   - 
     -------- 
       8      <--- Hasil sisa bagi
```

Jadi, 32 % 12 = 8

Contribute by: [Ferdy Nicolas](https://www.linkedin.com/in/ferdy-nicolas-348373196/)
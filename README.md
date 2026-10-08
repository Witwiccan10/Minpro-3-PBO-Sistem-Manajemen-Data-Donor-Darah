# Minpro-3-PBO-Sistem-Manajemen-Data-Donor-Darah

**Nama:** Muhammad Kevin Athfalyuna  
**Kelas:** B  
**Mata Kuliah:** Pemrograman Berorientasi Objek

## Deskripsi Singkat Program

Sistem Manajemen Data Donor Darah merupakan program berbasis Java yang digunakan untuk mengelola data pendonor, petugas, dan kegiatan donor darah.

Program ini merupakan pengembangan dari Mini Project 2 dengan menambahkan penerapan polymorphism, abstraction, serta struktur proyek MVC.

Program memiliki fitur untuk menambah, menampilkan, mengubah, dan menghapus data pendonor, petugas, serta kegiatan donor darah.

---

# Struktur Package

Struktur package pada program terdiri dari:

```text
src/main/java
│
├── controller
│   ├── DonorController.java
│   ├── PendonorController.java
│   └── PetugasController.java
│
├── main
│   └── Main.java
│
├── model
│   ├── Donor.java
│   ├── Identifiable.java
│   ├── Orang.java
│   ├── Pendonor.java
│   └── Petugas.java
│
└── view
    └── MenuView.java
```

### Model

Package `model` berisi class yang merepresentasikan data dalam program.

- `Orang` merupakan abstract class yang menjadi superclass dari `Pendonor` dan `Petugas`.
- `Pendonor` digunakan untuk menyimpan data pendonor.
- `Petugas` digunakan untuk menyimpan data petugas.
- `Donor` digunakan untuk menyimpan data kegiatan donor darah.
- `Identifiable` merupakan interface yang mendefinisikan method `getId()`.

### Controller

Package `controller` digunakan untuk mengatur proses pengelolaan data.

- `PendonorController` mengelola data pendonor.
- `PetugasController` mengelola data petugas.
- `DonorController` mengelola data donor.

### View

Package `view` berisi `MenuView` yang digunakan untuk menampilkan menu dan menerima input dari pengguna.

### Main

Package `main` berisi `Main.java` sebagai titik awal program dijalankan.

---

# Alur Program

## 1. Menu Utama

<img width="470" height="235" alt="image" src="https://github.com/user-attachments/assets/5056c5a8-cf3c-4481-83ad-2f29ed1baad1" />

**Gambar 1. Menu Utama Program**

Menu utama merupakan tampilan awal program yang menyediakan pilihan untuk mengelola data pendonor, petugas, dan kegiatan donor darah.

---

## 2. Menampilkan Data Pendonor

<img width="420" height="143" alt="AdobeExpressPhotos_df1220f1044841549b80adf3e8018c11_CopyEdited" src="https://github.com/user-attachments/assets/edd75006-b4bf-4101-9b94-63393c158ea1" />

**Gambar 2. Menampilkan Data Pendonor**

Menu ini digunakan untuk menampilkan data pendonor yang telah tersimpan di dalam program.

Data pendonor terdiri dari ID, nama, nomor HP, dan golongan darah.

---

## 3. Menampilkan Data Petugas

<img width="408" height="144" alt="AdobeExpressPhotos_a391dc3608ee4d5197af4d64e6bd0175_CopyEdited" src="https://github.com/user-attachments/assets/ff748eac-7512-4b6b-9df1-1a97d03e2393" />

**Gambar 3. Menampilkan Data Petugas**

Menu ini digunakan untuk menampilkan data petugas yang tersimpan dalam program.

Data petugas terdiri dari ID, nama, nomor HP, dan jabatan.

---

## 4. Menampilkan Data Donor

<img width="413" height="168" alt="AdobeExpressPhotos_a9db24723bb24828b7e18e3c12dc2bc4_CopyEdited" src="https://github.com/user-attachments/assets/654351b7-1010-4289-911b-c21a1f9a311a" />

**Gambar 4. Menampilkan Data Donor**

Menu ini digunakan untuk menampilkan data kegiatan donor darah.

Data donor terdiri dari ID donor, pendonor, petugas, tanggal donor, dan jumlah darah.

---

## 5. Menambahkan Data

<img width="387" height="197" alt="image" src="https://github.com/user-attachments/assets/95f508e2-7d56-4c62-92a1-929180c6e185" />

**Gambar 5. Menambahkan Data**

Pengguna dapat menambahkan data baru melalui menu yang tersedia. Data yang dimasukkan akan disimpan ke dalam `ArrayList`.

---

## 6. Mengubah Data

<img width="455" height="341" alt="image" src="https://github.com/user-attachments/assets/4637e0d3-1553-48fd-98e7-be9edb387e1a" />

**Gambar 6. Mengubah Data**

Fitur update digunakan untuk mengubah data yang telah tersimpan berdasarkan ID data.

---

## 7. Menghapus Data

<img width="383" height="72" alt="AdobeExpressPhotos_68c59eca9db64adc97c93d39e25c0887_CopyEdited" src="https://github.com/user-attachments/assets/38657aa9-fb07-4616-b3bf-3725c9d625f5" />

**Gambar 7. Menghapus Data**

Fitur hapus digunakan untuk menghapus data yang dipilih oleh pengguna dari daftar data.

---

# Penerapan Encapsulation

Encapsulation diterapkan dengan menggunakan access modifier `private` pada atribut class.

Contohnya pada class `Orang`:

```java
private String id;
private String nama;
private String noHp;
```

Atribut tersebut tidak dapat diakses secara langsung dari luar class. Pengaksesan data dilakukan menggunakan getter dan setter.

Contoh:

```java
public String getNama() {
    return nama;
}

public void setNama(String nama) {
    this.nama = nama;
}
```

Dengan demikian, data pada object dapat dikontrol melalui method yang telah disediakan.

---

# Penerapan Inheritance

Inheritance diterapkan dengan menggunakan class `Orang` sebagai superclass dan `Pendonor` serta `Petugas` sebagai subclass.

Struktur inheritance:

```text
             Orang
            /     \
       Pendonor   Petugas
```

Class `Pendonor`:

```java
public class Pendonor extends Orang
```

Class `Petugas`:

```java
public class Petugas extends Orang
```

Atribut umum seperti ID, nama, dan nomor HP berada pada superclass `Orang`, sedangkan atribut khusus berada pada masing-masing subclass.

---

# Penerapan Abstraction

Abstraction diterapkan menggunakan abstract class dan abstract method.

Class `Orang` dibuat sebagai abstract class:

```java
public abstract class Orang
```

Class tersebut memiliki abstract method:

```java
public abstract String getInfo();
```

Method `getInfo()` tidak memiliki implementasi pada class `Orang`. Implementasi method tersebut diberikan oleh subclass `Pendonor` dan `Petugas`.

Dengan demikian, `Orang` menjadi dasar umum yang harus diikuti oleh class turunannya.

---

# Penerapan Polymorphism

## 1. Overriding

Overriding diterapkan pada method `getInfo()`.

Pada class `Pendonor`:

```java
@Override
public String getInfo() {
    return "ID Pendonor    : " + getId()
            + "\nNama           : " + getNama()
            + "\nNo. HP         : " + getNoHp()
            + "\nGolongan Darah : " + golonganDarah;
}
```

Pada class `Petugas`:

```java
@Override
public String getInfo() {
    return "ID Petugas     : " + getId()
            + "\nNama           : " + getNama()
            + "\nNo. HP         : " + getNoHp()
            + "\nJabatan        : " + jabatan;
}
```

Kedua subclass memiliki method `getInfo()` dengan nama dan parameter yang sama, tetapi menghasilkan informasi sesuai dengan jenis object masing-masing.

---

## 2. Overloading

Overloading diterapkan pada method `cariDonor()` di `DonorController`.

Method pertama digunakan untuk mencari berdasarkan ID:

```java
public Donor cariDonor(String idDonor)
```

Method kedua digunakan untuk mencari berdasarkan ID dan tanggal:

```java
public Donor cariDonor(String idDonor, String tanggalDonor)
```

Kedua method memiliki nama yang sama tetapi parameter yang berbeda. Hal tersebut merupakan penerapan polymorphism melalui method overloading.

---

# Penerapan MVC

Program menggunakan struktur Model-View-Controller (MVC).

### Model

Model berisi object dan data program seperti:

- `Orang`
- `Pendonor`
- `Petugas`
- `Donor`

### View

View berisi `MenuView.java` yang bertanggung jawab terhadap tampilan menu dan input pengguna.

### Controller

Controller bertanggung jawab terhadap proses pengelolaan data melalui:

- `PendonorController`
- `PetugasController`
- `DonorController`

Pemisahan tersebut membuat setiap bagian program memiliki tanggung jawab yang berbeda sehingga struktur program menjadi lebih terorganisir.

---

# Nilai Tambah - Interface

Program menerapkan interface sebagai nilai tambah menggunakan interface `Identifiable`.

```java
public interface Identifiable {

    String getId();
}
```

Interface tersebut kemudian diterapkan pada abstract class `Orang`:

```java
public abstract class Orang implements Identifiable
```

Class `Orang` memiliki method `getId()` yang memenuhi method yang didefinisikan oleh interface `Identifiable`.

Interface digunakan untuk memberikan aturan bahwa object yang mengimplementasikan `Identifiable` harus menyediakan method `getId()`.

---

# Validasi Input

Program juga menerapkan validasi input untuk mencegah data yang tidak sesuai.

Contoh validasi yang diterapkan adalah:

- Input tidak boleh kosong.
- ID tidak boleh duplikat.
- Data harus sesuai dengan tipe input yang dibutuhkan.

<img width="377" height="291" alt="image" src="https://github.com/user-attachments/assets/18978a4c-d343-4743-b26b-a0b5c795c66c" />

**Gambar 8. Validasi Input**

Pada gambar tersebut program menolak input yang tidak sesuai dan meminta pengguna memasukkan data kembali.

---

# Dummy Data

Program memiliki dummy data yang digunakan sebagai data awal ketika program dijalankan.

Dummy data digunakan agar pengguna dapat langsung melihat contoh data tanpa harus memasukkan seluruh data dari awal.

Contoh data awal:

```text
Pendonor : P001
Petugas  : PT001
Donor    : D001
```

---

# Kesimpulan

Mini Project 3 merupakan pengembangan dari Mini Project 2 dengan penambahan konsep Pemrograman Berorientasi Objek berupa abstraction, polymorphism melalui overriding dan overloading, serta penerapan struktur MVC.

Program juga tetap menerapkan encapsulation dan inheritance yang telah digunakan pada pengembangan sebelumnya.

Sebagai nilai tambah, program menerapkan interface `Identifiable`.

---

# **SISTEM BOOKING LAPANGAN BADMINTON - Mini Project 3**

**Nama: Iqbal Nurriz Ramadhan**  
**NIM: 2509116067**
**Kelas: Sistem Informasi (B)**

## 1. Deskripsi Singkat Program
Program ini merupakan sistem berbasis Java yang dibuat untuk memenuhi tugas Mini Project 3 Pemrograman Berorientasi Objek (PBO). Sistem ini bertujuan untuk membantu pengelolaan data customer, lapangan, dan pemesanan lapangan badminton secara terstruktur.

Sistem Booking Lapangan Badminton dibuat berbasis CLI (Command Line Interface) dan menyimpan data secara sementara menggunakan ArrayList. Program menerapkan konsep OOP seperti encapsulation, inheritance, polymorphism, abstraction, serta menggunakan struktur MVC (Model, View, Controller). Sebagai nilai tambah, program juga menerapkan interface.

## 2. Penjelasan Struktur Package
Struktur project dibagi menggunakan pola MVC agar setiap bagian program memiliki tanggung jawab yang jelas.

  <img width="288" height="272" alt="image" src="https://github.com/user-attachments/assets/499ebd61-a745-41ea-9edb-91124abe0496" />

- **Model:** Menyimpan class yang merepresentasikan data program seperti Customer, Member, NonMember, Lapangan, dan Booking. Interface InfoCustomer juga berada pada package ini.
- **View:** Menampilkan menu, menerima input user, melakukan validasi input dasar, dan menampilkan output program.
- **Controller:** Mengatur proses pengolahan data seperti pencarian, penambahan, update, hapus booking, validasi data, dan perhitungan total harga.
- **Main:** Menjalankan BookingController dan BookingView sebagai awal program.

## 3. Penjelasan Alur Program
### 3.1. **Inisialisasi Awal**
   - Program membuat ArrayList untuk menyimpan data Customer, Lapangan, dan Booking.
   - Terdapat dummy data Customer, Lapangan, dan Booking agar data dapat langsung ditampilkan dan diuji saat program dijalankan.
   - Customer dibagi menjadi dua jenis, yaitu Member dan Non Member.
   - Tersedia beberapa lapangan dengan jenis karpet Vinyl dan Wooden.

### 3.2. **Menu Utama**
   - Program menggunakan perulangan while dan percabangan switch-case untuk menampilkan menu pilihan 1–8 sampai user memilih keluar.

   <img width="312" height="207" alt="image" src="https://github.com/user-attachments/assets/0f2af432-8a6b-4a14-9cc2-5fbe82a9357f" />


### 3.3. **Tambah Customer**
   - User memasukkan ID Customer, nama, nomor HP, serta memilih jenis Customer.
   - Jika memilih Member, user memasukkan diskon dengan batas 0% sampai 50%.
   - Jika memilih Non Member, user memasukkan biaya tambahan.
   - ID Customer tidak boleh duplikat, nama harus mengandung huruf, dan nomor HP hanya boleh berisi angka.

   <img width="240" height="242" alt="image" src="https://github.com/user-attachments/assets/b0f400a8-4c67-49eb-8ad1-17ff3346ec42" />


### 3.4. **Tampilkan Customer**
   - Menampilkan data ID, nama, nomor HP, dan status Customer.
   - Status Customer diperoleh dari method getStatus() yang diterapkan pada Member dan NonMember.

   <img width="450" height="158" alt="image" src="https://github.com/user-attachments/assets/c8c12e84-e790-4914-833e-b94e2fbed908" />


### 3.5. **Tampilkan Lapangan**
   - Menampilkan nomor lapangan, jenis karpet, dan harga sewa per jam.

   <img width="390" height="166" alt="image" src="https://github.com/user-attachments/assets/d75bba55-89d2-4bd9-93ac-2f2fbbb94976" />


### 3.6. **Tambah Booking**
   - User memilih Customer dan nomor lapangan yang tersedia.
   - Sistem menerima input durasi bermain, jam mulai, dan tanggal booking.
   - Kode booking dibuat berdasarkan ID Customer dan nomor lapangan.
   - Sistem menghitung total harga berdasarkan durasi, harga lapangan, diskon Member, atau biaya tambahan Non Member.

   <img width="446" height="463" alt="image" src="https://github.com/user-attachments/assets/93ceb8e6-199a-42f3-912c-ca28cb380f87" />


### 3.7. **Tampilkan Booking**
   - Menampilkan seluruh data booking seperti kode booking, ID Customer, nomor lapangan, durasi, jam mulai, tanggal, dan total harga.

   <img width="972" height="100" alt="image" src="https://github.com/user-attachments/assets/c23bd8a4-356e-478e-843a-f97c3c77ce43" />


### 3.8. **Update Booking**
   - User memasukkan kode booking yang ingin diubah, lalu memasukkan data booking baru.
   - Jika data valid, sistem memperbarui booking dan menghitung ulang total harga.

   <img width="970" height="310" alt="image" src="https://github.com/user-attachments/assets/bfbf19b8-71d0-4bfe-86fb-3e00efcb9116" />

   Hasil setelah data diperbarui:

   <img width="969" height="99" alt="image" src="https://github.com/user-attachments/assets/6d2803d7-f6a4-416a-a6af-3fae2699776c" />


### 3.9. **Hapus Booking**
   - User memasukkan kode booking yang ingin dihapus.
   - Jika ditemukan, data booking akan dihapus dari listBooking.

   <img width="975" height="131" alt="image" src="https://github.com/user-attachments/assets/e8128ceb-a6c6-42b7-adf6-340332fa7ff2" />

   Daftar booking setelah dihapus:

   <img width="969" height="96" alt="image" src="https://github.com/user-attachments/assets/1cf64724-87f2-485c-95b4-43a61e45e9b8" />


### 3.10. **Keluar**
  - Program berhenti ketika user memilih menu 8.

  <img width="377" height="231" alt="image" src="https://github.com/user-attachments/assets/79f027f3-1912-471b-b47e-c4f67a3d6dac" />


## 4. Encapsulation
Encapsulation diterapkan dengan menggunakan access modifier private pada atribut di setiap class. Data diakses melalui getter dan diubah melalui setter agar perubahan data tetap terkontrol.

Contoh:

```java
private final String idCustomer;
private String namaCustomer;
private String noHp;
```

Atribut yang digunakan sebagai identitas utama seperti idCustomer dibuat final dan tidak memiliki setter sehingga tidak dapat diubah setelah object dibuat.

Contoh getter dan setter:

```java
public String getNamaCustomer() {
    return namaCustomer;
}

public void setNamaCustomer(String namaCustomer) {
    this.namaCustomer = namaCustomer;
}
```

Validasi juga diterapkan pada input dan setter tertentu agar data yang masuk tetap sesuai, seperti nama harus mengandung huruf dan nomor HP hanya boleh berisi angka.


### 5. Inheritance
Inheritance diterapkan pada abstract class Customer sebagai superclass, kemudian diturunkan menjadi dua subclass yaitu Member dan NonMember.

```text
Customer (Abstract Superclass)
|__Member
|__ NonMember
```

Customer menyimpan atribut umum seperti ID Customer, nama Customer, dan nomor HP. Sedangkan subclass memiliki atribut khusus masing-masing:

- Member memiliki atribut diskon.
- NonMember memiliki atribut biayaTambahan.

Contoh:

```java
public class Member extends Customer
```

```java
public class NonMember extends Customer
```

## 6. Polymorphism 

### 6.1. Polymorphism (Overriding)
Polymorphism overriding diterapkan melalui method yang didefinisikan pada superclass/interface kemudian diimplementasikan kembali pada subclass.

Method hitungDiskon() pada Customer dibuat sebagai abstract method:

```java
public abstract double hitungDiskon();
```

Kemudian di-override pada Member:

```java
@Override
public double hitungDiskon() {
    return diskon;
}
```

Sedangkan pada NonMember:

```java
@Override
public double hitungDiskon() {
    return 0;
}
```

Jadi, pemanggilan customer.hitungDiskon() dapat memberikan hasil berbeda sesuai objectnya, apakah Member atau NonMember.

Method getStatus() juga di-override untuk menghasilkan status yang berbeda pada masing-masing jenis Customer.

### 6.2. Polymorphism - Overloading
Method overloading diterapkan pada method hitungHargaTotal() di BookingController dengan nama method yang sama tetapi parameter berbeda.

```java
public double hitungHargaTotal(Booking booking)
```

```java
public double hitungHargaTotal(Booking booking, double potonganTambahan)
```

Method pertama digunakan untuk menghitung harga booking normal, sedangkan method kedua dapat digunakan ketika terdapat potongan tambahan.

## 7. Abstraction
Abstraction diterapkan dengan menjadikan Customer sebagai abstract class.

```java
public abstract class Customer implements InfoCustomer
```

Class Customer tidak dapat dibuat object secara langsung. Object Customer harus dibuat melalui subclass seperti Member atau NonMember.

Selain itu, method hitungDiskon() dibuat sebagai abstract method agar setiap subclass wajib memberikan implementasinya sendiri.

## 8. Interface (Nilai Tambah)
Nilai tambah pada program ini diterapkan melalui interface InfoCustomer yang berada di package model.

<img width="337" height="127" alt="image" src="https://github.com/user-attachments/assets/d39b2d73-8136-4bc9-b75a-15c2327913b5" />

```java
public interface InfoCustomer {
    String getStatus();
}
```

Interface tersebut digunakan oleh abstract class Customer:

```java
public abstract class Customer implements InfoCustomer
```

Kemudian subclass Member dan NonMember memberikan implementasi getStatus() masing-masing.

Contoh pada Member:

```java
@Override
public String getStatus() {
    return "Member";
}
```

Contoh pada NonMember:

```java
@Override
public String getStatus() {
    return "Non Member";
}
```

Dengan interface ini, status Customer dapat dipanggil melalui method yang sama tanpa perlu lagi menentukan jenis object secara manual pada bagian View.



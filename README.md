# Muhammad-Azmi-Arya-Guna_2310010370_4C_PBO1
# Proyek Akhir Pemrograman Berbasis Objek 1

Proyek ini adalah contoh sederhana aplikasi pengolahan data Pegawai menggunakan Java sebagai tugas akhir dari mata kuliah pemrograman berbasis objek 1.

## Deskripsi

Aplikasi ini adalah program berbasis Java console yang digunakan untuk mencatat dan menampilkan data pegawai dengan tipe pegawai "Tetap" dan "Kontrak". Aplikasi ini menampilkan informasi pegawai seperti nama, NIP, jenis pegawai, dan gaji, serta melakukan validasi agar gaji pegawai Kontrak tidak melebihi Rp 3.000.000, sementara pegawai Tetap bebas.

Aplikasi ini mengimplementasikan beberapa konsep penting dalam pemrograman berorientasi objek (OOP) seperti Class, Object, Atribut, Method Constructor, Method Mutator, Method Accessor, Encapsulation, Inheritance, Overloading, Overriding, Seleksi, Perulangan, IO Sederhana, Array, dan Error Handling.

## Penjelasan Kode

Berikut adalah bagian kode yang relevan dengan konsep OOP yang dijelaskan:

1. *Class* adalah template atau blueprint dari object. Pada kode ini, Pegawai, PegawaiDetail, dan MainPegawai adalah contoh dari class.

bash
public class Pegawai {

}


public class PegawaiDetail extends Pegawai {

}


public class MainKepegawaian {
    public static void main(String[] args) {
    }
}


2. *Object* adalah instance dari class. Pada kode ini, listpegawai1[i] = new PegawaiDetail(nama, nip, jenis, gaji); adalah contoh pembuatan object.

bash
listpegawai1[i] = new PegawaiDetail(nama, nip, jenis, gaji);


3. *Atribut* adalah variabel yang ada dalam class. Pada kode ini, nama, npm, jenis, dan gaji adalah contoh atribut.

bash
String nama;
String nip;
String jenis;
double gaji;


4. *Constructor* adalah method yang pertama kali dijalankan pada saat pembuatan object. Pada kode ini, constructor ada di dalam class Pegawai dan PegawaiDetail.

bash
public Pegawai(String nama, String nip) {
        this.nama = nama;
        this.nip = nip;
    }

public PegawaiDetail(String nama, String nip, String jenis, double gaji) {
        super(nama, nip);
        this.jenis = jenis;
        this.gaji = gaji;
    }


5. *Mutator* atau setter digunakan untuk mengubah nilai dari suatu atribut. Pada kode ini, setNama dan setNip adalah contoh method mutator.

bash
public void setNama(String nama) {
        this.nama = nama;
    }

public void setNip(String nip) {
        this.nip = nip;
    }


6. *Accessor* atau getter digunakan untuk mengambil nilai dari suatu atribut. Pada kode ini, getNama, getNip, getJenis, dan getGaji adalah contoh method accessor.

bash
public String getNama() {
        return nama;
    }

public String getNip() {
        return nip;
    }

public String getJenis() {
        return jenis;
    }

public double getGaji() {
        return gaji;
    }

7. *Encapsulation* adalah konsep menyembunyikan data dengan membuat atribut menjadi private dan hanya bisa diakses melalui method. Pada kode ini, atribut nama dan nip dienkapsulasi dan hanya bisa diakses melalui method getter dan setter.

bash
private String nama;
private String nip;


8. *Inheritance* adalah konsep di mana sebuah class bisa mewarisi property dan method dari class lain. Pada kode ini, PegawaiDetail mewarisi Pegawai dengan sintaks extends.

bash
public class PegawaiDetail extends Pegawai {
    ...
}


9. *Polymorphism* (polimorfisme) dalam pemrograman berorientasi objek (OOP) adalah konsep yang memungkinkan sebuah method memiliki banyak bentuk.
Dengan kata lain, method yang sama dapat berperilaku berbeda tergantung pada objeknya. Polymorphism dalam aplikasi ini diterapkan melalui overriding method tampilInfo() dari superclass Pegawai oleh subclass PegawaiDetail.

bash
@Override
    public void tampilInfo() {
        super.tampilInfo();
        System.out.println("Jenis Pegawai   : " + jenis);
        System.out.println("Gaji            : Rp " + gaji);
    }


10. *Seleksi* adalah statement kontrol yang digunakan untuk membuat keputusan berdasarkan kondisi. Aplikasi ini menggunakan seleksi (kondisi if) untuk memvalidasi input pengguna, khususnya pada bagian jenis pegawai dan gaji.
Seleksi digunakan untuk:
1. Memastikan jenis pegawai hanya bisa “Tetap” atau “Kontrak”
2. Memastikan gaji pegawai Kontrak tidak melebihi Rp 3.000.000,
3. sedangkan pegawai Tetap bebas gaji berapa saja

bash
while(true){
                System.out.println("Jenis (Tetap/Kontrak): ");
                jenis = scanner.nextLine();
                // percabangan
                if(jenis.equalsIgnoreCase("Tetap") || jenis.equalsIgnoreCase("Kontrak")){
                    break;
                } else{
                    System.out.println("Input tidak valid!");
                }
            }

double gaji = 0;
            
            while (true) {
                try {
                    System.out.print("Gaji: ");
                    gaji = Double.parseDouble(scanner.nextLine());
                    if (jenis.equalsIgnoreCase("Kontrak") && gaji > 3000000) {
                        // Error Handling
                        throw new Exception("Gaji pegawai Kontrak tidak boleh lebih dari 3.000.000!");
                    }
                    break;
                } catch (NumberFormatException e){
                    System.out.println("Kesalahan format nomor");
                } catch (Exception e) {
                    System.out.println("Error: " + e.getMessage());
                }
            }


11. *Perulangan* adalah statement kontrol yang digunakan untuk menjalankan blok kode berulang kali. Pada kode ini, digunakan loop for untuk meminta input dan menampilkan data.

bash
for(int i = 0; i < listpegawai1.length; i++){
            System.out.println("\nPegawai ke-" + (i + 1)); // 1., 2., dst...(jika length ingin ditambah)
            
            System.out.println("Nama Pegawai: ");
            String nama = scanner.nextLine();
            
            System.out.println("NIP Pegawai: ");
            String nip = scanner.nextLine();
            
            String jenis = "";

for(PegawaiDetail data : listpegawai1){
            data.tampilInfo();
            System.out.println("----------------------");
        }


12. *Input Output Sederhana* digunakan untuk menerima input dari user dan menampilkan output ke user. Pada kode ini, digunakan class Scanner untuk menerima input dan method System.out.println untuk menampilkan output.

bash
Scanner scanner = new Scanner(System.in);
System.out.println("\nPegawai ke-" + (i + 1)); // 1., 2., dst...(jika length ingin ditambah)           
System.out.println("Nama Pegawai: ");
String nama = scanner.nextLine();           
System.out.println("NIP Pegawai: ");
String nip = scanner.nextLine();


13. *Array* adalah struktur data yang digunakan untuk menyimpan beberapa nilai dalam satu variabel. Aplikasi ini menggunakan array bertipe objek untuk menyimpan data beberapa pegawai. Array digunakan agar program dapat menyimpan dan mengelola banyak data pegawai secara efisien.
14. 
bash
PegawaiDetail[] listpegawai1 = new PegawaiDetail[2]; //lenght


15. *Error Handling* digunakan untuk menangani error yang mungkin terjadi saat runtime. Pada kode ini, digunakan try catch untuk menangani error.

bash
try {
    System.out.print("Gaji: ");
    gaji = Double.parseDouble(scanner.nextLine());
    if (jenis.equalsIgnoreCase("Kontrak") && gaji > 3000000) {
        // Error Handling
        throw new Exception("Gaji pegawai Kontrak tidak boleh lebih dari 3.000.000!");
    }
    break;
} catch (NumberFormatException e){
    System.out.println("Kesalahan format nomor");
} catch (Exception e) {
    System.out.println("Error: " + e.getMessage());
}
}


## Usulan nilai

| No  | Materi         |  Nilai  |
| :-: | -------------- | :-----: |
|  1  | Class          |    5    |
|  2  | Object         |    5    |
|  3  | Atribut        |    5    |
|  4  | Constructor    |    5    |
|  5  | Mutator        |    5    |
|  6  | Accessor       |    5    |
|  7  | Encapsulation  |    5    |
|  8  | Inheritance    |    5    |
|  9  | Polymorphism   |   10    |
| 10  | Seleksi        |    5    |
| 11  | Perulangan     |    5    |
| 12  | IO Sederhana   |   10    |
| 13  | Array          |   15    |
| 14  | Error Handling |   15    |
|     | *TOTAL*      | *100* |

## Pembuat

Nama: Muhammad Azmi Arya Guna
NPM: 2310010370

Nama : Amrina Rosyada Zikri
NIM : 09011282328055
Kelas : SK1A
Ujian : Pemrograman Komputer

import java.util.Scanner;
import java.util.ArrayList;

public class diskon {
    public static void main(String[] args) throws Exception {
        Scanner inputStr = new Scanner(System.in);
        Scanner inputInt = new Scanner(System.in);
        ArrayList<String> nama_barang = new ArrayList<>();
        ArrayList<Integer> harga_barang = new ArrayList<>();

        System.out.println("Masukkan jumlah barang : ");
        int jumlah_barang = inputInt.nextInt();

        for(int i = 0; i < jumlah_barang; i++){
            System.out.println("Masukkan nama barang : ");
            String input_barang = inputStr.nextLine();
            nama_barang.add(i, input_barang);
            System.out.println("Masukkan harga barang : ");
            int input_harga = inputInt.nextInt();
            harga_barang.add(i, input_harga);
            System.out.println();
        }
    
        int jumlah = 0; 
        for (int y = 0; y < jumlah_barang; y++){
            jumlah += harga_barang.get(y);
        }

        System.out.println("Barang belanja : " + nama_barang);
        System.out.println();

        if(nama_barang.size() < 5){
            System.out.println("Tidak Ada Diskon");
            System.out.println("Total harga : " + jumlah);
        }

        else if ((nama_barang.size() >= 5) && (nama_barang.size() <= 10)){
            int diskon = jumlah*5/100;
            int total_harga = jumlah-diskon;
            System.out.println("Total harga : " + total_harga);
        }

        else if ((nama_barang.size() >= 11) && (nama_barang.size() <= 20)){
            int diskon = jumlah*(10/100);
            int total_harga = jumlah-diskon;
            System.out.println("Total harga : " + total_harga);
        }

        else if ((nama_barang.size() > 20)){
            int diskon = jumlah*(20/100);
            int total_harga = jumlah-diskon;
            System.out.println("Total harga : " + total_harga);
        }

       
            inputStr.close();
            inputInt.close();
    }
}


public class autentikasi{
 public static void main(String[] args) {
  Scanner input = new Scanner(System.in);
  String username = "admin";
  String password = "admin";
 
  System.out.println("Masukkan username : ");
  String inputUsername = input.nextLine();
  System.out.println("Masukkan password : ");
  String inputPassword = input.nextLine();
  System.out.println( );
  
  if (inputUsername.equals(username) && inputPassword.equals(password)){
   System.out.println("Autentikasi berhasil");
  }
  else {
      System.out.println("Autentikasi gagal");
  }  
  input.close();
 
 }
}

import java.util.Scanner;
import java.util.LinkedList;

public class fibonacci {
 public static void main(String[] args) {
  Scanner input = new Scanner(System.in);
  LinkedList<Integer> deretFibonacci = new LinkedList<>();
  System.out.println("Deret Fibonacci hingga suku : ");
  int n = input.nextInt();
  int a = 0;
  int b = 1; 
  deretFibonacci.add(0, b);
  for (int i = 1; i<n; i++){
   int fibonacci = a+b;
   deretFibonacci.add(i, fibonacci); 
         a = b;
         b = fibonacci;
   }
  System.out.println("Deret Fibonacci adalah = " + deretFibonacci);
  input.close();
 }
}

import java.util.Scanner;

public class faktorisasi {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Masukkan angka: ");
        int angka = input.nextInt();

        System.out.print("Faktorisasi " + angka + ": ");
        faktor(angka);

        input.close();
    }

    static int faktor(int angka) {
        for (int i = 2; i <= angka; i++) {
            while (angka % i == 0) {
                System.out.print(i);
                angka = angka/i;
                if (angka > 1) {

                    System.out.print(" * ");
                }
            }
        }
        return angka;
    }
}

import java.util.Scanner;

public class operasi {
    static double penjumlahan(double angka1, double angka2){
        double hasil = angka1 + angka2;
        return hasil;
    }

    static double pengurangan(double angka1, double angka2){
        double hasil = angka1 - angka2;
        return hasil;
    }

    static double perkalian(double angka1, double angka2){
        double hasil = angka1 * angka2;
        return hasil;
    }
    static double pembagian(double angka1, double angka2){
        double hasil = angka1 / angka2;
        return hasil;
    }

    public static void main(String[] args){
    Scanner input = new Scanner(System.in);
    System.out.println("Masukkan angka 1 : ");
    double angka_pertama = input.nextInt();
    System.out.println("Masukkan angka 2 : ");
    double angka_kedua = input.nextInt();

    System.out.println("Pilihan operasi");
    System.out.println("1. Penjumlahan");
    System.out.println("2. Pengurangan");
    System.out.println("3. Perkalian");
    System.out.println("4. Pembagian");
    System.out.println();
    System.out.println("Masukkan pilihan operasi matematika");
    int pilihan = input.nextInt();

    switch (pilihan) {
        case 1 :
        System.out.println("Hasil Penjumlahan : " + penjumlahan(angka_pertama,angka_kedua));
        break;

        case 2 :
        System.out.println("Hasil Pengurangan : " + pengurangan(angka_pertama,angka_kedua));
        break;

        case 3 :
        System.out.println("Hasil Perkalian : " + perkalian(angka_pertama,angka_kedua));
        break;

        case 4 :
        System.out.println("Hasil Pembagian : " + pembagian(angka_pertama,angka_kedua));
        break;

        default :
        System.out.println("no output");
        break;
    }

    input.close();

    }
}

import java.util.Scanner;

public class palindrom {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        System.out.print("Masukkan kata atau frase: ");
        String input = scan.nextLine();
        if (isPalindrom(input)) {
            System.out.println("Kata atau frase tersebut adalah palindrom.");
        } else {
            System.out.println("Kata atau frase tersebut bukan palindrom.");
        }
        scan.close();
    }

    static boolean isPalindrom(String str) {
        str = str.replaceAll("\\s", "").toLowerCase();
        int i = 0;
        int j = str.length() - 1;

        while (i < j) {
            if (str.charAt(i) != str.charAt(j)) {
                return false;
            }
            i++;
            j--;
        }
        return true;
    }
}

import java.util.Scanner;
import java.util.Scanner;

public class perpustakaanmethod {
    public static String info_judul(String judul){
       return judul;
    }
    public static String info_penulis(String penulis){
       return penulis;
    }
    public static int info_tahunterbit(int tahun_terbit){
       return tahun_terbit;
    }
    public static boolean info_status(boolean status){
        return status;
    }

    public static void main (String[] args){
        Scanner input = new Scanner (System.in);
        Scanner inputInt = new Scanner(System.in);
        System.out.println("Masukkan judul buku : ");
        String judul = input.nextLine();
        System.out.println("Masukkan penulis buku : ");
        String penulis = input.nextLine();
        System.out.println("Masukkan tahun terbit buku : ");
        int tahun_terbit = inputInt.nextInt();
        boolean status = true;
        
        System.out.println();
        System.out.println("INFO BUKU");
        System.out.println("============================");
        System.out.println("Judul buku = " + info_judul(judul));
        System.out.println("Penulis buku = " + info_penulis(penulis));
        System.out.println("Tahun terbit buku = " + info_tahunterbit(tahun_terbit));
        if (status == true){
            System.out.println("Status buku = tersedia");
        }

        System.out.println("Ingin Meminjam?");
        String pinjam_buku = input.nextLine();
        if (pinjam_buku.equals("ya")){
            System.out.println("Masukkan tanggal peminjaman (note : peminjaman maksimal 2 minggu) : ");
            int tanggal_pinjam = inputInt.nextInt();
            System.out.println("Masukkan tanggal pengembalian : ");
            int tanggal_kembali = inputInt.nextInt();
            System.out.println("tanggal pinjam : " + tanggal_pinjam + "| tanggal kembali : " + tanggal_kembali + "| peminjaman berhasil");
            boolean status_terbaru = info_status(!status);
            System.out.println();

            System.out.println("INFO BUKU");
            System.out.println("============================");
            System.out.println("Judul buku = " + info_judul(judul));
            System.out.println("Penulis buku = " + info_penulis(penulis));
            System.out.println("Tahun terbit buku = " + info_tahunterbit(tahun_terbit));
            if (status_terbaru != status){
            System.out.println("Status buku = tidak tersedia");
            }
        }
        else {
            System.out.println("end");
        }

        input.close();
        inputInt.close();
    }     
}

class AkunPengguna {
    private String username;
    private String password;
    private boolean aktif;

    public AkunPengguna(String username, String password) {
        this.username = username;
        this.password = password;
        this.aktif = true; 
    }

    public void InfoAkun() {
        System.out.println("Username: " + username);
        System.out.println("Password: " + password);
        System.out.println("Status: " + (aktif ? "Aktif" : "Nonaktif"));
        System.out.println();
    }

    public void aktifkanAkun() {
        if (!aktif) {
            aktif = true;
            System.out.println("Akun berhasil diaktifkan.");
        } else {
            System.out.println("Akun sudah aktif.");
        }
    }

    public void nonaktifkanAkun() {
        if (aktif) {
            aktif = false;
            System.out.println("Akun berhasil dinonaktifkan.");
        } else {
            System.out.println("Akun sudah nonaktif.");
        }
    }
}

public class akun {
    public static void main(String[] args) {
        AkunPengguna akun1 = new AkunPengguna("admin", "admin");
        System.out.println("Informasi Akun 1:");
        akun1.InfoAkun();
        akun1.aktifkanAkun();
        System.out.println("Informasi Akun 1 setelah diaktifkan:");
        akun1.InfoAkun();
        akun1.nonaktifkanAkun();
        System.out.println("Informasi Akun 1 setelah dinonaktifkan:");
        akun1.InfoAkun();
    }
}

import java.util.Stack;
import java.util.Scanner;
public class stack {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.println("Masukkan kurung : ");
        String ekspresi = input.nextLine();
        if (cekUrutanKurung(ekspresi)) {
            System.out.println("Urutan kurung benar.");
        } else {
            System.out.println("Urutan kurung salah.");
        }
        input.close();
    }

    static boolean cekUrutanKurung(String ekspresi) {
        Stack<Character> stack = new Stack<>();

        for (char karakter : ekspresi.toCharArray()) {
            if (karakter == '(') {
                stack.push(karakter);
            } else if (karakter == ')') {
                if (stack.isEmpty() || stack.pop() != '(') {
                    return false; 
                }
            }
        }
        return stack.isEmpty(); 
    }
}



# Aplikasi Pertambahan Dua Angka

**Tugas Pemrograman GUI**  
Nama: Atma Fathul Hadi  
NPM: 2210010425  

## 1. Deskripsi Program
Aplikasi ini adalah program berbasis GUI menggunakan Java yang memungkinkan pengguna untuk menjumlahkan dua angka yang diinputkan. Program ini juga menyediakan tombol untuk menghapus input, mengulang masukan angka, dan keluar dari aplikasi.

## 2. Komponen GUI
Aplikasi ini menggunakan komponen GUI berikut:

- **JFrame**: Sebagai jendela utama aplikasi.
- **JPanel**: Untuk mengatur layout dan grup komponen.
- **JLabel**: Menampilkan label teks, seperti judul aplikasi dan label input.
- **JTextField**: Tempat untuk memasukkan angka yang ingin dijumlahkan.
- **JButton**: Tombol untuk melakukan perhitungan, menghapus input, dan keluar dari aplikasi.
- **JOptionPane**: Menampilkan pesan pop-up yang menunjukkan hasil penjumlahan atau pesan error jika input tidak valid.

## 3. Logika Program
Program ini menerima input dua angka dari pengguna, kemudian menambahkan kedua angka tersebut dan menampilkan hasilnya dalam dialog pop-up. Jika input bukan angka, program akan menampilkan pesan error.

### Kode Terkait:
- **Fungsi untuk Menjumlahkan Dua Angka**  
  Kode berikut digunakan untuk mengambil dua angka dari input, menjumlahkannya, dan menampilkan hasilnya menggunakan `JOptionPane`:
  ```java
  hitung.addActionListener(new ActionListener() {
      public void actionPerformed(ActionEvent evt) {
          try {
              int num1 = Integer.parseInt(a1.getText());
              int num2 = Integer.parseInt(a2.getText());
              int sum = num1 + num2;
              JOptionPane.showMessageDialog(null, "Hasil: " + sum, "Hasil Penjumlahan", JOptionPane.INFORMATION_MESSAGE);
          } catch (NumberFormatException e) {
              JOptionPane.showMessageDialog(null, "Masukkan angka yang valid", "Error", JOptionPane.ERROR_MESSAGE);
          }
      }
  });
  ```
  
- **Event untuk Tombol Keluar**  
  Tombol keluar akan menutup aplikasi saat diklik:
  ```java
  keluar.addActionListener(new ActionListener() {
      public void actionPerformed(ActionEvent evt) {
          System.exit(0);
      }
  });
  ```

- **Pembatasan Input Hanya Angka**  
  Menggunakan `KeyAdapter` untuk memastikan hanya angka yang dapat dimasukkan di `JTextField`:
  ```java
  a1.addKeyListener(new KeyAdapter() {
      public void keyTyped(KeyEvent evt) {
          if (!Character.isDigit(evt.getKeyChar())) {
              evt.consume();
          }
      }
  });

  a2.addKeyListener(new KeyAdapter() {
      public void keyTyped(KeyEvent evt) {
          if (!Character.isDigit(evt.getKeyChar())) {
              evt.consume();
          }
      }
  });
  ```

## 4. Cara Menjalankan Program
1. Buka program di IDE seperti NetBeans atau Eclipse.
2. Jalankan program.
3. Masukkan dua angka pada kolom input.
4. Klik tombol "HITUNG" untuk menghitung hasil penjumlahan angka tersebut.
5. Hasil perhitungan akan ditampilkan di kotak dialog pop-up.
6. Klik "HAPUS" untuk membersihkan input dan mengulang memasukkan angka.
7. Klik "KELUAR" untuk menutup aplikasi.

## 5. Struktur Program
- **APDA.java**: Berisi kode utama untuk aplikasi, termasuk komponen GUI dan logika pemrosesan angka.

Screenshot Hasil Program:
![Screenshot](https://github.com/atmafathulhadi/PBO-Latihan1-AplikasiPertambahanDuaAngka/blob/main/S.png)

## 6. Indikator Penilaian
| No  | Komponen         |  Persentase  |
| :-: | ---------------- |   :-----:    |
|  1  | Komponen GUI     |    20%       |
|  2  | Logika Program   |    20%       |
|  3  | Events           |    15%       |
|  4  | Kesesuaian UI    |    15%       |
|  5  | Memenuhi Variasi |    30%       |
|     | **TOTAL**        |    100%      |

---

Aplikasi ini menyediakan antarmuka sederhana yang memungkinkan pengguna untuk melakukan penjumlahan dua angka secara interaktif dan memastikan pengalaman pengguna yang baik dengan validasi input dan pesan error yang jelas.

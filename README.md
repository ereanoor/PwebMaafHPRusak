# Penjelasan Kode
Program ini dibuat menggunakan Node.js untuk menentukan zodiak berdasarkan input tanggal dan bulan dari pengguna melalui terminal.

## 1. Inisialisasi Modul Readline
```JavaScript
const readline = require("readline");

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout
});
```
```require("readline")```: Mengambil modul bawaan Node.js untuk menangani input dan output teks secara interaktif di terminal.

```readline.createInterface```: Mengonfigurasi program agar bisa menerima input dari keyboard (stdin) dan menampilkan teks ke layar (stdout).

## 2. Fungsi Logika Zodiak
```JavaScript
function tentukanZodiak(tanggal, bulan) { ... }
```
Fungsi ini bertugas sebagai "mesin" utama program. Di dalamnya terdapat serangkaian pengondisian ```(if...else if)``` yang membandingkan variabel tanggal dan bulan dengan rentang tanggal masing-masing zodiak. Jika input tidak masuk ke kategori manapun, fungsi akan mengembalikan pesan error.

## 3. Menangkap Input Pengguna
```JavaScript
rl.question("Masukkan tanggal lahir (1-31): ", function (tanggal) {
  rl.question("Masukkan bulan lahir (1-12): ", function (bulan) { ... });
});
```
```rl.question```: Menampilkan pertanyaan di terminal dan menunggu pengguna mengetik jawaban.

Karena proses ini bersifat asynchronous, kita menggunakan callback function di dalam fungsi lainnya untuk menanyakan bulan setelah tanggal diisi.

## 4. Konversi dan Validasi Data
```JavaScript
tanggal = parseInt(tanggal);
bulan = parseInt(bulan);

if (isNaN(tanggal) || isNaN(bulan) || tanggal < 1 || tanggal > 31 || bulan < 1 || bulan > 12) {
  console.log("Input tidak valid!");
}
```
```parseInt```: Mengubah input dari user (yang awalnya berupa teks/string) menjadi angka utuh agar bisa dihitung secara matematis.

```isNaN```: Memeriksa apakah input yang dimasukkan benar-benar angka. Jika user memasukkan huruf, program akan memberikan peringatan "Input tidak valid".

Program juga memastikan angka tanggal berada di rentang 1–31 dan bulan 1–12.

## 5. Menampilkan Hasil dan Menutup Program
```JavaScript
const zodiak = tentukanZodiak(tanggal, bulan);
console.log("\nTanggal Lahir:", tanggal + "/" + bulan);
console.log("Zodiak:", zodiak);
rl.close();
```
Setelah validasi lolos, program memanggil fungsi tentukanZodiak dan mencetak hasilnya ke terminal.

```rl.close()```: Sangat penting untuk mematikan interface readline agar program berhenti dengan benar dan tidak terus menunggu input di terminal.

## 3 Output Kode
<img width="1067" height="674" alt="Screenshot 2026-02-22 202202" src="https://github.com/user-attachments/assets/6f34d005-35d5-450d-b6d3-cda7f7e00c33" />

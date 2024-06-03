<div align="center">
  <h1 style="text-align: center;font-weight: bold">Praktikum 11<br>Praktek Sistem Operasi</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : </h3>
  <p style="text-align: center;">
    <strong>Adrian Yoga Chrisarianto (3123500021) </strong><br>
  </p>
<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
  <hr>
</div>

# Mutex (Analisa Soal 2)

## Program Tanpa Mutex

### Output

![App Screenshot](asset/1.png)

### Analisa

program pertama tidak menggunakan mutex
yang berakibat pada terjadinya race condition hyang mana thread bersaing untuk mengakses dan
memodifikasi nilai shared_counter secara bersamaan karena tidak ada sinkronisasi akses terhadap
variabel global shared_counter.

## Program Dengan Mutex

### Output 

![App Screenshot](asset/2.png)

### Analisa

program kedua menggunakan mutex untuk sinkronisasi akses ke variabel
shared_counter. penggunaan mutex pada program kedua memberikan pencegaan dari terjadinya race
condition dan memastikan bahwa operasi penambahan shared_counter dilakukan secara atomik, agar
menghasilkan hasil yang konsisten.

### Kesimpulan

Adanya mutex menyebabkan jika sebuah thread ingin mengakses shared_counter, Thread harus
mengunci mutex dahulu dengan menggunakan pthread_mutex_lock(). Setelah selesai, thread akan
melepaskan kunci mutex dengan pthread_mutex_unlock(). Dengan menggunakan mutex, hanya satu
thread yang dapat mengakses atau memodifikasi shared_counter pada satu waktu, sehingga
memastikan konsistensi nilai dan mencegah race conditio
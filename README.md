# Module 10 - Asynchronous Programming - Timer

> ##### Nanda Nathaniela Meizari - 2206824136

## Experiment 1.2: Understanding how it works
![Experiment 1.2: Understanding how it works](assets/images/Experiment%201.2.jpg)
Dilihat pada gambar, terlihat bahwa print "hey hey" muncul sebelum "howdy!" dan "done!". Print ini ditulis di thread utama, bukan dalam tugas asinkron. Jadi, hingga `run()` pada executor dipanggil, pemanggilan `spawner.spawn(async {...});` belum akan menjalankan tugasnya tersebut

## 1.3. Multiple Spawn and removing drop
![Experiment 1.3: Multiple Spawn and removing drop](assets/images/Experiment%201.3.jpg)
Dari output yang terlihat di gambar, program tidak berhenti. Hal ini disebabkan oleh fungsi `drop` yang tidak dijalankan, sehingga executor tidak mendapat indikasi bahwa antrian tidak akan menerima tugas tambahan. Selain itu, urutan eksekusi tugas tampak tidak konsisten, yang bisa jadi dikarenakan algoritma penjadwalan yang digunakan oleh executor. Meskipun eksekusi tugas mungkin berurutan, pesan yang dicetak tidak selalu muncul secara berurutan. Setiap tugas yang dibuat oleh spawner menggunakan sumber daya, dan jika dibuat dalam jumlah banyak, program akan berjalan lebih lama dan executor mungkin akan mengalami kesulitan dalam mengelola banyak tugas.
# Module 10 - Asynchronous Programming - Timer

> ##### Nanda Nathaniela Meizari - 2206824136

## Experiment 1.2: Understanding how it works
![Experiment 1.2: Understanding how it works](assets/images/Experiment%201.2.jpg)
Dilihat pada gambar, terlihat bahwa print "hey hey" muncul sebelum "howdy!" dan "done!". Print ini ditulis di thread utama, bukan dalam tugas asinkron. Jadi, hingga `run()` pada executor dipanggil, pemanggilan `spawner.spawn(async {...});` belum akan menjalankan tugasnya tersebut
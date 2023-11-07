![Dynamic Routing](1.png)

# PENGERTIAN
- Routing adalah sebuah proses untuk meneruskan paket-paket jaringan dari satu jaringan ke jaringan lainnya melalui sebuah internetwork. Routing juga dapat merujuk kepada sebuah metode penggabungan beberapa jaringan sehingga paket-paket data dapat hinggap dari satu jaringan ke jaringan selanjutnya. Untuk melakukan hal ini, digunakanlah sebuah perangkat jaringan yang disebut sebagai router. Router- router tersebut akan menerima paket-paket yang ditujukan ke jaringan di luar jaringan yang pertama, dan akan meneruskan paket yang ia terima kepada router lainnya hingga sampai kepada tujuannya. Routing protokol berbeda dengan router protokol. Routing protokol adalah komunikasi antara router. Routing protokol mengijinkan router untuk sharing informasi tentang jaringan dan koneksi antar router. Router menggunakan informasi ini untuk membangun dan memperbaiki tabel routingnya. Ada beberapa dynamic routing untuk IP.
- Protokol ini didesain untuk mendistribusikan informasi yang secara dinamis mengikuti perubahan kondisi jaringan. Protokol routing mengatasi situasi routing yang kompleks secara cepat dan akurat. Protokol routing didesain tidak hanya untuk mengubah ke rute backup bila rute utama tidak berhasil, namun juga didesain untuk menentukan rute mana yang terbaik untuk mencapai tujuan tersebut.
- Dynamic routing adalah sebuah metode dalam jaringan komputer di mana perangkat jaringan secara otomatis memutuskan jalur terbaik untuk mengirim data berdasarkan informasi yang diperoleh secara dinamis dari jaringan. Dalam konteks ini, "dinamis" berarti bahwa konfigurasi jaringan dapat berubah seiring waktu karena berbagai faktor, seperti perubahan topologi jaringan, kepadatan lalu lintas, atau kegagalan perangkat jaringan. 
* Kelebihan
- Cocok untuk area besar/luas
- Hanya mengenalkan alamat yang terhubung langsung dengan routernya
- Bila terjadi penambahan suatu network baru tidak perlu semua router dikonfigurasi, hanya router yang berkaitan saja
- Router secara otomatis berbagi informasi
* Kekurangan
- Beban kerja router menjadi lebih berat karena selalu memperbarui IP table pada setiap waktu tertentu
- Kecepatan pengenalan dan kelengkapan IP table memakan waktu lama karena router akan melakukan broadcast ke semua router sampai ada IP table yang cocok

# Jenis Protokol

* RIP (Routing Information Protocol)
RIP merupakan protokol yang memberikan routing table berdasarkan router yang terhubung langsung. Lalu, router selanjutnya akan memberikan informasi ke router selanjutnya yang terhubung langsung dengan router tersebut. Adapun informasi yang diberikan dalam protokol RIP yaitu: host, network, subnet, dan route default
RIP terbagi menjadi dua bagian, yaitu:
* RIPv1 (RIP versi 1)
- Hanya mendukung routing class-full
- Tidak ada info subnet yang dimasukkan dalam data perbaikan routing
* RIPv2 (RIP versi 2)
- Mendukung routing class-full dan class-less
- Info subnet dimasukkan dalam data perbaikan routing
* persamaan RIPv2 lainnya dengan RIPv1, di antaranya:
- Distance Vector Routing Protocol
- Metric berupa hop count
- Max hop count adalah 15
* Sedangkan perbedaan RIPv2 dengan RIPv1 adalah sebagai berikut:
- Bersifat class-less routing protocol, yang berarti RIPv2 menyertakan field SM dalam paket update yang dikirimkan sehingga RIPv2 dapat mendukung VLSM & CIDR
- Mengirimkan paket update & menerima paket update versi 2
- Mengirimkan update ke alamat multicast yaitu 224.0.0.9
* Kelebihan
- Menggunakan metode “Triggered Update”.
- Memiliki timer untuk mengetahui kapan router harus kembali memberikan informasi routing
* Kekurangan
- Jumlah host yang terbatas.
- Tidak memiliki informasi tentang subnet setiap route.
- Tidak mendukung Variable Length Subnet Masking (VLSM).

* IGRP (Interior Gateway Routing Protocol)
IGRP adalah sebuah routing protocol yang dikembangkan pada pertengahan tahun 1980-an oleh Cisco Systems Inc. Tujuan utama penciptaan IGRP adalah untuk menyediakan protokol yang kuat untuk routing dalam sistem otonomi. IGRP memiliki hop maksimum 255, tetapi defaultnya sendiri adalah 100. IGRP menggunakan bandwidth dan garis menunda secara default untuk menentukan rute terbaik dalam sebuah internetwork (Composite Metrik). Karena protocol ini diciptakan oleh Cisco, maka di dalam kumpulan perintah dasar Cisco terdapat perintah untuk mengatur protokol ini.
* Kelebihan
- Mendukung sampai 255 hop count
* Kekurangan
- Jumlah host yang terbatas
- Produk Cisco

* OSPF (Open Short Path First)
OSPF adalah sebuah routing protocol standar terbuka yang telah diaplikasikan oleh sejumlah vendor jaringan dan dijelaskan di RFC 2328. Jika Anda memiliki banyak router, dan tidak semuanya adalah router Cisco, maka Anda tidak dapat menggunakan IGRP. jadi pilihan Anda tinggal RIP v1, RIP v2, atau OSPF. Jika jaringan yang dikelola adalah jaringan besar, maka OSPF adalah pilihan satu-satunya. OSPF ini adalah sesuatu yang disebut route redistribution, yaitu sebuah layanan penerjemah antar routing protocol
* Kelebihan
- Tidak menghasilkan routing loop
- Mendukung penggunaan beberapa metrik sekaligus Bisa menghasilkan banyak jalur ke sebuah tujuan membagi jaringan yang besar mejadi beberapa area
- Waktu yang diperlukan untuk konvergen lebih cepat.
* Kekurangan
- Membutuhkan basis data yang besar.
- Lebih rumit

* EIGRP (Enhanced Interior Gateway Routing Protocol)
Protokol routing ini menggunakan algoritma advanced distance vector dan menggunakan cost load balancing yang tidak sama. Algoritma yang dipakai adalah kombinasi antara distance vector dan link-state, serta menggunakan Diffusing Update Algorithm (DUAL) untuk menghitung jalur terpendek. Distance vector protocol merawat satu set metric yang kompleks untuk jarak tempuh ke jaringan lainnya.
IGRP dan EIGRP sama-sama sudah mempertimbangkan masalah bandwitdh yang ada dan delay yang terjadi.
* Kelebihan
- Melakukan konvergensi secara tepat ketika menghindari loop.
- Memerlukan lebih sedikit memori dan proses.
- Adanya fitur "loop avoidance".
* Kekurangan
- Hanya dapat digunakan untuk Router Cisco

* BGP (Border Gateway Protocol)
BGP merupakan salah satu jenis routing protocol yang ada di dunia komunikasi data. Sebagai routing protocol, BGP memiliki kemampuan untuk melakukan pengumpulan rute, pertukaran rute dan menentukan rute terbaik menuju ke sebuah lokasi dalam sebuah jaringan. Routing protocol juga pasti dilengkapi dengan algoritma yang pintar dalam mencari jalan terbaik. Namun yang membedakan BGP dengan routing protocol lain adalah BGP termasuk ke dalam kategori routing protocol jenis Exterior Gateway Protocol (EGP).
* Kelebihan
- Sangat sederhana dalam instalasi
* Kekurangan
- Sangat terbatas dalam mempergunakan topologi jaringan
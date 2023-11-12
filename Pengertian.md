# Pengertian CI/CD
Saat ini, sebagian besar perusahaan sudah memulai perjalanan transformasi digital mereka untuk membangun hubungan lebih erat dengan pelanggan/pengguna guna mencapai nilai bisnis yang berkelanjutan. Tak hanya itu, perusahaan-perusahaan tersebut (apa pun jenis dan skala bisnisnya) juga berkompetisi dengan pesaing mereka. Salah satu strateginya adalah memasuki market (pasar bisnis) dengan berinovasi lebih cepat daripada sebelumnya. Dengan begitu, mereka bisa memenangkan persaingan bisnis.

Maka dari itu, penting bagi para perusahaan tersebut untuk tetap fokus pada penciptaan inovasi dan peningkatan kualitas perangkat lunak. Hal itu tak bisa dilakukan dengan cara “lama” nan tradisional sehingga mereka perlu merampingkan software delivery (pengiriman/penyajian perangkat lunak).

Oleh karena itu, DevOps pun hadir. DevOps ditujukan untuk membawa Developer ke dunia IT Operations; dan IT Operations ke dunia Developer. Koneksi yang lebih baik ini menghasilkan produk perangkat lunak yang lebih mudah digunakan dan memenuhi kebutuhan dengan lebih baik.

Selain itu, DevOps membantu meningkatkan kemampuan perusahaan dalam menghadirkan aplikasi dan layanan dengan kualitas tinggi serta waktu rilis yang cepat. Tentu saja siapa pun di dunia ini ingin memiliki proses deploy yang cepat seraya menjaga infrastruktur tetap aman.

Mengadopsi budaya automasi adalah kunci untuk mencapai DevOps yang baik. Dengan automasi, muncul kepercayaan diri. Dengan percaya diri, muncul optimalisasi proses sehingga menghasilkan aplikasi atau perangkat lunak yang berkualitas dengan cepat. Salah satu strateginya, selain hanya memikirkan soal deployment, perusahaan juga mesti menguji aplikasi sekomprehensif mungkin agar dapat disajikan ke pengguna sesuai ekspektasi tanpa melahirkan gangguan pada sistem yang ada.

Nah, sebab itulah praktik CI/CD kini ramai diterapkan di banyak perusahaan. Praktik CI/CD terbukti mampu membawa perubahan yang berarti bagi perusahaan dan membuat mereka menjadi percaya diri dalam bersaing di pasar bisnis.

Anda pun sebagai developer jangan sampai ketinggalan, ya. Anda wajib memahami CI/CD jika ingin unggul dari para developer lain di luar sana.

Sebagaimana tersurat pada namanya, CI/CD terdiri dari 2 akronim: CI dan CD. Kita akan bedah satu per satu. Mari awali dengan menilik CI terlebih dahulu.

## Continuous Integration (CI)
Continuous integration (biasa disingkat CI) merupakan praktik pengembangan aplikasi/perangkat lunak di mana Developer secara teratur (atau sesering mungkin) mengunggah (push) atau menggabungkan (merge) perubahan kode (code changes) mereka ke sebuah repositori terpusat (central repository) dan/atau ke mainline trunk (seperti branch master/main), setelah itu proses pembentukan (build) dan pengujian (test) secara otomatis akan dijalankan [1].

Tujuan utama dari continuous integration adalah untuk menemukan dan mengatasi bug lebih cepat, meningkatkan kualitas perangkat lunak, dan mengurangi waktu yang diperlukan untuk memvalidasi dan merilis pembaruan perangkat lunak baru.

Selain itu, dengan continuous integration, developer bisa cepat menerima respons apakah kode yang mereka tulis sesuai ekspektasi atau tidak. Tak perlu lagi harus menunggu berhari-hari hanya untuk diberi tahu tim QA apakah Developer bisa lanjut mengerjakan fitur selanjutnya atau perlu berkutat memperbaiki eror.

Ada beberapa kategori tools yang bisa kita manfaatkan untuk menghadirkan CI untuk aplikasi yang dibuat, antara lain sebagai berikut.

- Source control version management
  
Ini digunakan untuk berkomunikasi dan menyelesaikan konflik kode antara beberapa developer yang bekerja di basis kode (codebase) yang sama. Salah satu tools yang kerap digunakan dan populer adalah git. Bila Anda ingin tahu lebih dalam soal git, silakan akses kelas Belajar Dasar Git dengan GitHub.

Saat menggunakan source control version management seperti git, Anda disarankan untuk melakukan perubahan sekecil mungkin dan mengintegrasikan perubahan tersebut sesering mungkin.


- Build automation
  
Dalam konteks pengembangan aplikasi, “build” mengacu pada proses yang mengubah file dan aset lainnya menjadi produk perangkat lunak dalam bentuk final atau siap di-deploy. Sementara itu, file hasil dari proses build disebut “build artifact”, umumnya termasuk package, compressed file, container image, dll.

Ada serangkaian langkah yang akan dibutuhkan untuk membuat sebuah build artifact. Proses pembentukan build artifact dilakukan secara otomatis, semisal ketika developer mengunggah (push) kode ke central repository atau saat menggabungkan (merge) kode ke main branch. Banyak tools yang kerap dipakai untuk build automation, salah satunya yang ternama ialah Jenkins.


- Automated testing
  
Testing alias pengujian menjadi hal yang penting karena bertindak untuk memastikan/memvalidasi basis kode berfungsi dengan benar tanpa bug dan/atau tidak menyebabkan regresi pada fitur yang ada. Testing yang dilakukan pada tahapan CI umumnya adalah unit test.

Sama seperti proses build (karena sering kali dilakukan beriringan), pengujian ini juga dilakukan secara otomatis setiap kali developer mengunggah (push) kode ke central repository atau saat menggabungkan (merge) kode ke main branch. Jika aplikasi tidak perlu di-build, proses yang dilakukan hanya testing. Karena dilakukan bersamaan, biasanya tools untuk automasi build dan test pun sama, misalnya Jenkins.

Automated testing ini juga menghasilkan suatu artifact, bisa berupa test result, code coverage, dan lain sebagainya. Dengan demikian, artifact tidak hanya ada dalam proses build, melainkan juga bisa dibuat saat proses testing. Kita akan bahas lebih dalam soal ini nanti.

Semoga Anda sudah paham dengan CI, intinya proses yang terintegrasi biasanya adalah building dan testing (berupa unit test). Selanjutnya, mari kita tilik apa yang dimaksud dengan CD.

## Continuous Delivery/Deployment (CD)

Bila CI berarti continuous integration, CD memiliki dua arti: continuous delivery atau continuous deployment. Ini semua tergantung pada prosesnya.

Continuous delivery adalah perpanjangan dari continuous integration karena secara otomatis melakukan deploy terhadap semua perubahan kode ke testing dan/atau production environment sesaat setelah tahapan build usai dan/atau lolos test [2]. Jika diterapkan dengan benar, developer akan selalu memiliki produk build yang siap deploy yang telah melewati proses pengujian standar. 

Continuous delivery menggunakan pendekatan di mana suatu persetujuan manual (manual approval) perlu dilakukan sebelum proses deploy ke production environment guna memastikan bahwa perubahan kode benar-benar siap disajikan ke pengguna. Dengan ini, Anda dapat men-deploy aplikasi kapan pun hanya dengan mengeklik suatu tombol.

Secara teori, dengan continuous delivery, Anda dapat memutuskan untuk men-deploy setiap hari, setiap minggu, setiap dua minggu, atau kapan pun sesuai kebutuhan bisnis. Namun, jika Anda benar-benar ingin mendapatkan manfaat dari continuous delivery, Anda harus men-deploy ke production environment sedini mungkin untuk memastikan bahwa Anda men-deploy aplikasi dalam skala batch yang kecil sehingga mudah untuk diperbaiki jika terjadi masalah.

Continuous delivery memungkinkan Developer mengotomatiskan pengujian bahkan di luar unit test saja sehingga mereka dapat memverifikasi pembaruan aplikasi di berbagai dimensi. Pengujian ini dapat mencakup UI testing, load testing, integration testing, API reliability testing, dll. Hal ini membantu Developer untuk memvalidasi pembaruan secara lebih menyeluruh sehingga mereka dapat menemukan masalah dengan cepat.

Continuous deployment berjalan satu langkah lebih jauh daripada continuous delivery. Continuous deployment adalah praktik yang berupaya mengotomatiskan deployment produk dari awal hingga akhir. Dengan praktik ini, semua perubahan yang berhasil melewati setiap fase pada alur CI/CD akan langsung di-deploy ke production environment dan seketika tersaji ke pengguna. Tidak ada campur tangan manusia. Hanya pengujian yang gagal yang akan mencegah perubahan baru di-deploy ke production environment. 

Continuous deployment merupakan cara terbaik untuk mempercepat feedback loop (sudah kita pelajari di kelas Belajar Dasar-Dasar DevOps) dengan pengguna Anda. Selain itu, Developer bisa fokus pada pembuatan perangkat lunak, dan mereka dapat melihat pekerjaan masing-masing secara langsung hanya dalam waktu beberapa menit setelah selesai mengerjakannya. Keren, bukan?

Agar praktik ini dapat diterapkan dengan baik, tim wajib membuat skenario pengujian sekomprehensif mungkin dan sekaligus memiliki kepercayaan diri tinggi dalam proses automated testing. Tujuan utamanya, selama proses build telah lulus dari automated testing maka kode akan langsung di-deploy.

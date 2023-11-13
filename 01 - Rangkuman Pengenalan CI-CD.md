# Rangkuman Pengenalan CI/CD

## Pengertian CI/CD
Sebagaimana tersurat pada namanya, CI/CD terdiri dari 2 akronim: CI dan CD. Kita akan bedah satu per satu. Mari awali dengan menilik CI terlebih dahulu.

- Continuous Integration (CI)
  
Continuous integration (biasa disingkat CI) merupakan praktik pengembangan aplikasi/perangkat lunak di mana Developer secara teratur (atau sesering mungkin) mengunggah (push) atau menggabungkan (merge) perubahan kode (code changes) mereka ke sebuah repositori terpusat (central repository) dan/atau ke mainline trunk (seperti branch master/main), setelah itu proses pembentukan (build) dan pengujian (test) secara otomatis akan dijalankan. 

- Continuous Delivery/Deployment (CD)
  
Bila CI berarti continuous integration, CD memiliki dua arti: continuous delivery atau continuous deployment. Ini semua tergantung pada prosesnya.

Continuous delivery adalah perpanjangan dari continuous integration karena secara otomatis melakukan deploy terhadap semua perubahan kode ke testing dan/atau production environment sesaat setelah tahapan build dan/atau test usai. Jika diterapkan dengan benar, developer akan selalu memiliki produk build yang siap deploy yang telah melewati proses pengujian standar. 

Continuous delivery menggunakan pendekatan di mana suatu persetujuan manual (manual approval) perlu dilakukan sebelum proses deploy ke production environment guna memastikan bahwa perubahan kode benar-benar siap disajikan ke pengguna. Dengan ini, Anda dapat men-deploy aplikasi kapan pun hanya dengan mengklik suatu tombol.

Continuous deployment berjalan satu langkah lebih jauh daripada continuous delivery. Continuous deployment adalah praktik yang berupaya mengotomatiskan deployment produk dari awal hingga akhir. Dengan praktik ini, semua perubahan yang berhasil melewati setiap fase pada alur CI/CD akan langsung di-deploy ke production environment dan seketika tersaji ke pengguna. Tidak ada campur tangan manusia. Hanya pengujian yang gagal yang akan mencegah perubahan baru di-deploy ke production environment. 

- CI/CD Pipeline
  
Dengan istilah-istilah yang kita pelajari (continuous integration dan continuous delivery/deployment), lahirlah CI/CD Pipeline (atau DevOps Pipeline). Ia merupakan serangkaian langkah yang harus dilakukan untuk menghadirkan versi perangkat lunak yang baru. CI/CD Pipeline adalah praktik yang berfokus pada peningkatan software delivery (pengiriman perangkat lunak) di seluruh siklus pengembangan perangkat lunak (build, test, dan deploy kode) melalui automasi.


## Alur CI/CD
Alur CI/CD pada dasarnya memiliki 8 tahapan atau fase, antara lain Plan -> Code -> Build -> Test -> Release -> Deploy -> Operate -> Monitor. Masing-masing alur memiliki karakteristiknya sendiri yang perlu Anda pahami betul. Mari kita bahas.

- Plan
  
Tahapan “Plan” mencakup semua yang terjadi sebelum Developer mulai menulis kode. Segala persyaratan atau kebutuhan aplikasi dikumpulkan dari para stakeholder (pemangku kepentingan) dan klien/pelanggan/pengguna. 

- Code
  
Pada tahap ini, tim Developer menulis dan mengembangkan kode aplikasi dalam bahasa pemrograman tertentu, entah itu Java, JavaScript, Python, C#, dsb. Mereka menulis kode di lingkungan development agar segala perubahan atau penambahan fitur tak berimbas ke aplikasi yang dipakai pengguna, seperti misalnya di komputer pribadi menggunakan IDE alias Integrated Development Environment.

- Build
  
Dalam konteks pengembangan aplikasi, “build” mengacu pada proses yang mengubah file dan aset lainnya menjadi produk perangkat lunak dalam bentuk final atau siap di-deploy. Langkah-langkahnya sebagai berikut:

- Meng-compile kode
  
Memeriksa gaya dan standar dari kode.
Menganalisis tingkat kompleksitas dan pemeliharaan kode.
Memvalidasi dependencies pada kode.
Membuat sebuah artifact, seperti container image, compressed file (jar, zip, dll), installer, package, dan sebagainya.
Menjalankan unit test.


- Test
  
Setelah proses build sukses, artifact (artefak/arsip) build secara otomatis di-deploy ke testing atau staging environment untuk dilakukan pengujian yang lebih mendalam. Testing atau staging environment ini berupa server beserta konfigurasi dan komponen pendukung lainnya yang menyerupai production environment.

- Release
  
Tahapan Release adalah titik di mana tim bisa mengatakan bahwa artifact (artefak/arsip) build siap untuk di-deploy ke production environment. Pada tahap ini, setiap perubahan kode (code changes) telah melewati serangkaian pengujian manual ataupun otomatis dan tim telah yakin bahwa semuanya sudah aman sesuai ekspektasi. 

- Deploy
  
Setelah semua tahapan berhasil dijalankan dan lulus dari pengujian, akhirnya artifact build pun di-deploy ke production environment. Ada beberapa tools yang dapat mengotomatiskan proses pembuatan infrastruktur untuk production environment (dan juga testing atau staging environment), salah satunya adalah Infrastructure-as-Code (IaC). 

- Operate
  
Pada tahap ini, aplikasi (atau perubahan kode) sudah di-deploy dan bisa diakses oleh pengguna. Ingat! Pekerjaan tak berhenti sampai di sana. Kita perlu memastikan bahwa semuanya berjalan lancar tanpa ada gangguan atau kendala sedikitpun. Semisal, kita perlu mengonfigurasi agar aplikasi memiliki skalabilitas yang baik sehingga bisa memenuhi request pelanggan, sebanyak apa pun jumlahnya. Ini bagus untuk menghindari aplikasi down saat menghadapi banyaknya pengguna. Bayangkan saja, jika aplikasi Anda down, pengalaman pengguna terganggu dan tentu saja perusahaan akan rugi.

- Monitor
  
Fase “terakhir” dari siklus DevOps adalah memantau (monitor) environment. Tahap ini dibangun berdasarkan feedback pengguna yang diberikan dalam fase Operate dengan mengumpulkan data dan analitik tentang perilaku pengguna, kinerja, bug, dan lainnya. 

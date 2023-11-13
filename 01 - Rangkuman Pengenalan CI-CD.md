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

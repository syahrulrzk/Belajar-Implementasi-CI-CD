# Rangkuman Continuous Integration

## Pengenalan Integration
Integrasi berarti penggabungan kode baru atau perubahan kode yang ditulis oleh satu atau banyak kontributor (bisa Developer, IT Operations, Tester/QA, dsb) ke dalam satu proyek aplikasi atau perangkat lunak. Proses integrasi ini biasanya dilakukan dengan merge (menggabungkan) feature branch ke main branch melalui pull request.

Mari kita bahas soal git dan istilahnya lebih dalam.

### Pengenalan Git
  
Dengan version control seperti git, setiap Developer bisa berkolaborasi di codebase yang sama, melakukan tracking pada setiap perubahan, mengetahui siapa yang melakukan perubahan di kode, memisahkan pengerjaan fitur tertentu, dan masih banyak lagi.

Git dapat berjalan di komputer lokal ataupun server. Namun, bila aplikasinya dikembangkan oleh banyak developer, tentu membutuhkan git server atau git hosting agar source code yang dimiliki setiap developer bisa saling sinkron dan up-to-date.

Kita bisa membuat git server sendiri atau menggunakan layanan berbasis cloud seperti GitLab atau GitHub. Dengan git hosting tersebut, kita akan lebih mudah mengelola urusan repositori atau penyimpanan kodenya.

Bagi Anda yang belum terbiasa dengan git, berikut beberapa istilah dalam git yang perlu Anda ketahui agar tidak asing dengannya.

- Repository
  
Repository adalah istilah yang digunakan sebagai penyimpanan source code. Repository dapat bersifat local dan remote.

- Clone
  
Clone (cloning) adalah proses menyalin atau mengkloning repositori dari remote repository (misal, GitHub repository) ke local repository (komputer pribadi) untuk mempermudah penambahan, pengubahan, atau penghapusan kode; perbaikan konflik saat penggabungan branch (merge conflict); dan sebagainya.

- Branch
  
Sebagaimana yang kita tahu, git adalah version control system, di mana versioning ini salah satunya diatur oleh fitur branch (cabang). Setiap git repository memiliki minimal satu branch, yakni main branch (cabang utama).

- Commit
  
Commit merupakan sebuah aksi yang dilakukan Developer untuk membuat rekam jejak (snapshot) terhadap perubahan kode yang ia tulis.

- Push
  
Perintah git push merupakan tindakan lanjutan dari perintah git commit. Push merupakan aksi untuk mengirim perubahan kode dari local repository ke remote repository. Push dilakukan untuk memperbarui kode yang ada di remote dengan kode yang ada di local.

- Pull Request
  
Pull Request adalah sebuah pengajuan/permintaan (request) untuk menggabungkan perubahan kode pada suatu branch ke branch lain.

- Merge
  
Merge merupakan aksi untuk menggabungkan perubahan kode pada suatu branch ke branch lain. Merge dapat dilakukan melalui atau tanpa pull request.

Oke, sekarang Anda sudah kenal git dan beberapa istilahnya. Namun, itu semua masih belum cukup. Masih ada satu hal lagi yang perlu Anda pahami, yakni branching strategy.

### Branching Strategy
Karena praktik continuous integration erat kaitannya dengan “integration” seperti mengintegrasikan atau merge branch, kita perlu tahu apa saja jenis-jenis branching strategy yang acap dipakai untuk mengelola source code.

Branching strategy adalah strategi yang diadopsi oleh tim Developer saat menulis (coding), menggabungkan (merging), dan menggelar (deploy) kode menggunakan version control system.

Kita hanya akan bahas GitHub flow dan Trunk-based development.

- GitHub flow
  
Seperti yang tertulis jelas pada namanya, strategi ini diciptakan dan dipopulerkan oleh GitHub. Dengan GitHub flow, Developer akan memulai pengembangan aplikasi di main branch. Kemudian, jikalau ingin membuat fitur atau melakukan perubahan besar pada kode aplikasi, Developer perlu membuat branch baru (yang berasal dari main branch, disebut feature branch) guna mengisolasi pekerjaan mereka. Bila penulisan kode sudah selesai, feature branch tersebut lantas digabungkan kembali ke main branch; dan feature branch kemudian dihapus.

- Trunk-based development
  
Trunk-based development adalah branching strategy yang mendorong Developer untuk berkolaborasi pada kode di branch tunggal bernama “trunk” (alias “main” jika dalam nomenklatur git). Ide utama di balik strategi ini adalah agar Developer membuat perubahan kode dalam skala kecil dengan lebih sering. Tujuannya supaya Developer bisa lebih fokus dan lebih dekat dengan main branch, sekaligus mempercepat proses deploy sehingga Developer dapat langsung mengetahui hasil dari yang mereka tulis.

Pastikan Anda benar-benar paham sebelum lanjut ke materi berikutnya. 

### Hubungan Git dengan CI/CD

Build tools atau CI/CD tools memerlukan suatu mekanisme untuk mengetahui perubahan dari git server. Ada beberapa mekanisme yang sering digunakan, salah satunya melalui webhook dan pooling (cron).

Webhook terjadi saat ada perubahan dari git server dan kemudian mengirimkan pesan kepada build tools mengenai kejadian (event) yang terjadi pada git server tersebut. Lantas, build tools kemudian akan menanggapi sesuai dengan event yang dikirimkan. Contohnya, saat Developer melakukan commit, git server akan mengirimkan webhook ke build tools yang kemudian akan memulai proses build, test, dan deploy aplikasi.

Selain melalui webhook, build tools juga dapat melakukan pooling sehingga build tools inilah yang secara aktif membandingkan/melihat perubahan yang terjadi pada git server.

### Berkenalan dengan React App

React App adalah aplikasi web sederhana yang menampilkan halaman web dengan konten “Welcome to React” disertai dengan test (pengujian) untuk memeriksa apakah aplikasi me-render tampilan dengan baik. Selain itu, aplikasi ini akan menggunakan Node.js sebagai JavaScript runtime environment dan npm sebagai package manager.

Sebagaimana yang tadi sudah disebutkan, aplikasi React App akan berjalan di lokal. Tools yang akan kita pakai selama berinteraksi dengan React App (sekalian mengikuti alur CI/CD) adalah sebagai berikut.

- Code: Visual Studio Code sebagai Code Editor dan GitHub sebagai Git hosting platform (source control version management).

- Build dan Test: Jenkins sebagai tools untuk build automation, automated testing, sekaligus CI pipeline (meski bisa dimanfaatkan untuk keseluruhan proses pada CI/CD pipeline, modul ini hanya akan fokus untuk membuat CI pipeline).

Masing-masing tools akan dibahas lebih detail di materi berikutnya. Namun, masih ada satu tahapan yang kurang, yaitu kita belum mendefinisikan tools untuk tahapan Plan. 

- Tahapan Plan di React App
  
Saat kita berbicara mengenai tahapan Plan, akan erat kaitannya dengan project management tools. Ada banyak tools yang tersedia dan Anda bisa pilih sesuai kebutuhan.

Salah satu yang populer dan sering dipakai untuk software development adalah Jira Software. Pasalnya, tools ini memang ditujukan untuk Agile project management yang mana mendukung dan selaras dengan prinsip-prinsip DevOps. Dengan tools tersebut, Anda bisa memanfaatkan pendekatan Agile, melalui implementasi Scrum framework dengan membuat sprint, penggunaan Kanban framework untuk membuat kanban board, dan lain sebagainya.

### Continuous Integration dengan GitHub dan Jenkins

Secara umum, continuous integration memiliki alur mulai dari Plan, Code, Build, hingga Test. Untuk tahapan Plan, kita sudah membahas tools yang digunakan–yakni salah satunya dengan Jira Software–sekaligus mengenal kriteria dari aplikasi React App. Akan tetapi, kita belum dalami bagian Code, Build, dan Test. 

Kita baru menyebutkan bahwa untuk tahapan Code, tools yang dipakai di kelas ini adalah Visual Studio Code sebagai Code Editor dan GitHub sebagai Git hosting platform. Sementara itu, untuk fase Build dan Test, kita akan menggunakan Jenkins sebagai tools untuk build automation, automated testing, sekaligus CI pipeline.

Nah, sebelum praktik menggunakan tools-tools tersebut, di modul ini kita akan bahas masing-masing tools secara lebih mendalam. Mari kita mulai.

 - GitHub
   
GitHub adalah perusahaan yang menawarkan layanan Git repository hosting berbasis cloud. GitHub membuat para pengguna baik individu maupun tim menjadi lebih mudah untuk menggunakan git dalam mengontrol versi suatu pekerjaan (kode pemrograman, dokumen, dsb) saat melakukan kolaborasi dalam atau antar tim.

- Jenkins
  
Jenkins adalah tools otomatisasi open source yang dapat digunakan untuk mengotomatisasi semua jenis pekerjaan terkait building, testing, dan delivering/deploying perangkat lunak. 

Jenkins dapat diinstal di berbagai sistem operasi (Windows, Linux, macOS, FreeBSD, dll) melalui native package, Docker, Kubernetes, atau dijalankan secara mandiri (standalone) oleh mesin apa pun dengan WAR (Web application Archive) files.

### Berkenalan dengan Trivia App

Karena kita sudah menyelesaikan proyek React App, selanjutnya kita akan fokus berkenalan dengan Trivia App.

Ada yang berbeda dengan proyek Trivia App ini. Bila sebelumnya kita berlatih di local environment (komputer pribadi) dengan tools open source seperti Jenkins, kali ini kita akan menggunakan cloud provider ternama, yakni Amazon Web Services alias AWS.

Sebagaimana namanya, Trivia App adalah sebuah aplikasi permainan/kuis trivia yang akan memberikan 10 pertanyaan menarik. Pertanyaan yang disajikan adalah seputar ilmu geografi sederhana, yakni berkenaan dengan nama ibu kota dari suatu negara. Simpel nan mengasyikkan, bukan?

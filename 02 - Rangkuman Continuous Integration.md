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

### Continuous Integration di AWS
Fokus dari materi kali ini adalah membahas tools-tools yang akan kita pakai untuk membuat CI pipeline menggunakan beberapa layanan AWS, terutama untuk bagian Code, Build, dan Test.

Berikut beberapa layanan AWS yang akan digunakan untuk membuat CI Pipeline di kelas ini.

- Code: AWS Cloud9 sebagai cloud-based IDE dan AWS CodeCommit sebagai managed source control service untuk meng-hosting (menyimpan dan mengelola) private Git repositories.

- Build dan Test: AWS CodeBuild sebagai fully managed build service untuk meng-compile source code, menjalankan test, dan memproduksi software packages. 

- CI Pipeline: AWS CodePipeline sebagai fully managed CI/CD Pipeline service untuk membantu mengotomatiskan proses continuous integration dan continuous delivery/deployment aplikasi (meski bisa dimanfaatkan untuk keseluruhan proses pada CI/CD pipeline, modul ini hanya akan fokus untuk membuat CI pipeline).

Supaya lebih jelas, mari kita bahas setiap layanan satu per satu berdasarkan kategorinya, yakni Code, Build, dan Test.

### Continuous Integration di AWS: Code

Apabila pada proyek React App kita memakai Visual Studio Code dan GitHub, untuk proyek Trivia App di AWS, kita akan menggunakan AWS Cloud9 dan AWS CodeCommit.

- AWS Cloud9
  
Pada dasarnya, AWS Cloud9 adalah sebuah IDE atau integrated development environment berbasis cloud (bisa diakses kapan saja dan di mana saja melalui web browser). AWS Cloud9 membuat kolaborasi menjadi mudah. Anda dapat membagikan environment dengan orang lain untuk memungkinkan pair programming. Dengan begitu, anggota tim dapat saling melihat isi kode dan bersamaan melakukan coding secara real time. 

AWS Cloud9 sangat terintegrasi dengan AWS CodeCommit (mengingat keduanya adalah sama-sama layanan dari AWS) sehingga semakin memudahkan pekerjaan Developer.

- AWS CodeCommit
  
AWS CodeCommit adalah managed source control service (atau bisa juga disebut version control service) yang dapat digunakan untuk meng-hosting (menyimpan dan mengelola) private git repository (repository yang bersifat private). Kerennya, AWS CodeCommit mendukung semua fungsi standar yang ada pada git. Jadi, bila Anda familier dengan git repository, niscaya Anda juga akan terbiasa dengan AWS CodeCommit. 

Semoga Anda sudah paham dengan tools yang akan kita gunakan pada tahapan Code dari alur CI/CD aplikasi Trivia App.



### Continuous Integration di AWS: Build

Kita tahu bahwa proses dari build adalah mengambil kode (pull the code), mengompilasinya (compiling), dan menginstal dependencies package dari repository (seperti npm modules atau Java Maven artifact). Output dari proses build akan menjadi sebuah packaged artifact yang siap untuk deployment, bisa jadi Linux RPM package, Java WAR file, Docker image, Windows MSI installer, atau banyak lainnya. Package tersebut kemudian dapat diteruskan ke proses deployment untuk meluncurkan pembaruan aplikasi. 

Proses build umumnya juga menyertakan automated testing (pengujian otomatis) untuk memeriksa kualitas kode dan memastikan bahwa kode berjalan sesuai harapan, salah satunya adalah melalui unit test. Kita akan berbicara lebih banyak soal pengujian (test) nanti. 

Di AWS, terdapat layanan yang dapat membantu kita dalam urusan build sehingga memungkinkan continuous integration, ia adalah AWS CodeBuild. Layanan ini memungkinkan kita untuk meng-compile kode, menjalankan test, dan membuat deployment packages.

AWS CodeBuild adalah sebuah service alias layanan. Tak seperti mengelola proses build sendiri di local development environment, AWS CodeBuild memiliki skalabilitas yang baik sehingga dapat menjalankan beberapa proses build sekaligus. Itu artinya, ia tak akan membiarkan proses build Anda dalam antrean.



### Continuous Integration di AWS: Test

Jika kita ingin menerapkan CI/CD, jangan lupakan tentang testing (pengujian). Testing perlu diterapkan di berbagai tahapan dalam proses pengembangan aplikasi untuk menciptakan measure of quality (mengukur kualitas kode) pada setiap aspek aplikasi.

Ada beberapa jenis pengujian yang bisa Anda praktikkan, seperti regression test, integration test, dan unit test.

- Regression test: Jenis pengujian yang memeriksa/menguji setiap komponen aplikasi yang ada tidak rusak dengan adanya perubahan atau fitur baru. Misalnya, ketika Anda menambahkan fitur pembelian, pastikan bahwa fitur riwayat stok tidak bermasalah.

- Integration test: Jenis pengujian ini menguji beberapa modul yang saling berkaitan. Misal pada Trivia App, apakah permain berhasil berjalan? Apakah aplikasi dapat menampilkan jumlah pemain dengan benar? Apakah pertanyaan dikirim ke setiap pemain? Apakah skor dihitung dengan tepat? Semua rangkaian aspek-aspek tersebut diuji dalam satu kesatuan.

- Unit test: Jenis pengujian ini menguji fungsionalitas secara terpisah (satu unit, bukan menjadi satu kesatuan). Misal pada Trivia App, apakah skor dihitung dengan tepat?

Semoga kini Anda sudah paham ya soal testing.



### Continuous Integration di AWS: CI Pipeline

Setiap fase (Code, Build, dan Test) yang kita lakukan pada Trivia App masih manual. Lantas, bagaimana jika kita ingin menjalankan semuanya secara otomatis setiap kali commit kode? Jelas bahwa automasi diperlukan supaya kita bisa selalu menerima feedback (umpan balik) secara langsung yang menyatakan bahwa kode yang di-commit berfungsi dengan baik (kunci dari CI/CD).

Idealnya, kita memerlukan semacam workflow (alur kerja) sekaligus orchestrator (pengatur) yang dapat mengontrol setiap tahapan pada proses pengembangan aplikasi alias pipeline. Sebenarnya, ada banyak layanan yang dapat digunakan untuk mengatur langkah-langkah pada pipeline, tetapi yang akan kita bicarakan saat ini adalah AWS CodePipeline. 

AWS CodePipeline memungkinkan kita untuk membuat serangkaian langkah atau tahapan untuk mengimplementasikan CI/CD Pipeline. Dalam kasus Trivia App, kita ingin agar setiap kali Developer meng-commit perubahan kode ke repository akan secara otomatis memulai tahapan lain, yakni menjalankan test. 

AWS CodePipeline tidak melakukan semua ini sendirian. Seperti yang tadi disebutkan, ia adalah sebuah orchestrator. AWS CodePipeline bekerja sama dengan layanan AWS lain, seperti AWS CodeCommit (Code), AWS CodeBuild (Build & Test), dan AWS CodeDeploy (Deploy–nanti kita bahas) untuk menciptakan sebuah CI/CD Pipeline yang harmoni.

Menggunakan orchestrator seperti AWS CodePipeline penting bagi Anda yang ingin menerapkan DevOps. Musabab, ia dapat meningkatkan kecepatan dan kualitas pada pembaruan atau fitur aplikasi yang dikirim ke pengguna.


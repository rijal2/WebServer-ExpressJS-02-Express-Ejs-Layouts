# WebServer-ExpressJS-02-Express-Ejs-Layouts
Memanfaatkan NPM dari express untuk membuat halaman menjadi lebih fleksibel dan dinamis. Fasilitas yang digunakan adalah Express-ejs-layouts

1. Install express-ejs-layouts@2.5.0
    Untuk dokumentasi nya bisa cek disini:
    https://www.npmjs.com/package/express-ejs-layouts

2. Import express-ejs-layouts agar dikenali oleh file app.js
    const expressLayouts = require('express-ejs-layouts');
3. Cara konfigurasi (setup)
    masukkan metode dibawah ini
    app.use(expressLayouts);

CARA MENGGUNAKAN
1. Buat layout utama dengan nama main-layouts.ejs (namanya bebas). Sehingga kedepan sudah tidak membutuhkan lagi file header.ejs, footer.ejs.

2. Mengisi file main-layout.ejs dengan starter template dari bootstrap
3. Di dalam element body tambahkan tag ejs
    <%- body %>
    tag tersebut boleh disimpan didalam container atau diluar container.
    tulisan body pada tag tersbut akan menjadi tempat penyimpanan semua elemnt yang akan di import ke halaman main-layout

AGAR main-layout.ejs dapat menerima file-file yang akan di import
4. Memanggil File ejs agar bisa digunakan di main-layout.ejs.
5. Panggil element nav yang tersimpan pada file nav.ejs dengan menuliskan
    <%- include('nav') %>

    Tulisan yang berada di dalam kuurung merupakan alamat file yang relatif terhadap file main-layout.ejs
6. Pada file yang akan di import hapus semua metode include(). Sehingga menyisakan elemen utama nya saja.\
    Contoh:
    Pada halaman / file about.ejs. Di dalam file tersebut hanya tinggal elemen
    <h1>Ini adalah Halaman About dari file about.html</h1>

AGAR TITLE JUGA IKUT BERUBAH SESUAI HALAMAN YANG DI IMPORT
7. Tambahkan parameter yang berupa object pada metode res.render(). Sehingga parameter tersebut berisi properti title dan layouts. Properti title diisi dengan nama halaman, sedangkan layouts diisi dengan alamat file main-layouts.ejs yang relatif terhadap file yang akan diimport.
    Contoh:
    Halaman about
    app.get('/about', (req, res) => {
        res.render('about', {
        title: "Halaman About",
        layout: "layouts/main-layout"
        })
    })

8. Pada file main-layout.ejs ubah title nya dengan tag ejs
    <title><%= title %>  </title>
    Bertujuan agar nama title nya sesuai dengan yang disetting di app.get() nya

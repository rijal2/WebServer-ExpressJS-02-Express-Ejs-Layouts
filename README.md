# WebServer-ExpressJS-02-Express-Ejs-Layouts
Memanfaatkan NPM dari express untuk membuat halaman menjadi lebih fleksibel dan dinamis. Fasilitas yang digunakan adalah Express-ejs-layputs

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

2. 
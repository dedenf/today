---
title: "Publish Hugo dengan Netlify"
date: 2018-10-18T13:41:48+07:00
draft: false
---

Sebelumnya saya [menulis tentang Hugo](https://today.dedenf.com/posts/2018-10-17-setup-today-blog-dengan-hugo/), mesin blog yang saya gunakan untuk **blog today** ini, dan untuk mendeploy-nya di internet, menggunakan [Netlify](https://netlify.com), selain gratis (ada opsi bayar untuk fitur yang lebih *advance*), untuk *tier* gratisannya lumayan cukup untuk mengakomodasi kebutuhan *publishing*.

Untuk memulai, pastikan sudah mendaftar di netlify, disarankan juga untuk meng-*host* domain di netlify, jika tidak juga tidak apa-apa, bisa dilakukan registrasi di record CNAME nantinya, [lihat dokumentasi](https://www.netlify.com/docs/custom-domains/) untuk lebih jelasnya.

Proses publikasi juga cukup mudah, mulai dengan opsi "[New Site from Git](https://app.netlify.com/start)", kemudian pilih Git provider yang digunakan, saya menggunakan [Github](https://github.com/dedenf/today). Dari situ proses bisa dimulai dengan memilih *repo* yang digunakan untuk blog, 

![pilih repo](/images/choose-repo.png)

dan kemudian *build!*
![pilih repo](/images/build-site.png)

Jika belum *setup* domain, bisa dilanjutkan dengan domain yang diinginkan untuk didaftarkan ditahap ini.
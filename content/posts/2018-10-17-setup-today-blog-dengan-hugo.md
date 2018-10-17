---
title: "Setup Blog Dengan Hugo"
date: 2018-10-17T17:41:48+07:00
draft: false
---

Tidak seperti [blog](https://notes.dedenf.com) [yang](https://jakartadev.org) [lainnya](https://jenius.tech/) yang menggunakan [Jekyll](https://jekyllrb.com/) sebagai _blog engine_, di blog ini menggunakan [Hugo](https://gohugo.io/).

Hugo menurut saya sangan cepat, baik dari sisi setup, maupun dalam sisi deployment.

### Instalasi
Instalasi sangat mudah, jika pengguna macOS, cukup menggunakan [homebrew](https://brew.sh/), dan jalankan perintah
```shell
$ brew install hugo 
```
dan system yang akan mengurus semuanya, untuk system dan cara lain silakan lihat [didokumentasi](https://gohugo.io/getting-started/installing/).

Dan kemudian bisa melakukan perintah ini untuk melihat apakah site kita jalan dengan baik
```shell
$ hugo server
```
Jika berjalan normal, terminal akan memperlihatkan pesan seperti ini
```shell
                   | EN
+------------------+----+
  Pages            | 10
  Paginator pages  |  0
  Non-page files   |  0
  Static files     |  4
  Processed images |  0
  Aliases          |  4
  Sitemaps         |  1
  Cleaned          |  0

Total in 9 ms
```
Untuk melakukan kostumasi, bisa dilakukan edit file `config.toml`.

### Theme
Untuk instalasi tema juga mudah, kebetulan saya menggunakan [`hugo-paper`](https://github.com/nanxiaobei/hugo-paper/), cukup melakukan 
```shell
$ git clone https://github.com/nanxiaobei/hugo-paper.git themes/hugo-paper
```
Setelah itu jangan lupa untuk memanggil theme tersebut di `config.toml` dengan menambahkan entry 
```toml
...
theme = "hugo-paper"
```

### Menulis entry
Menulis entry blog pertama kali bisa dicoba dengan menggunakan perintah 
```shell
$ hugo new posts/entry-pertama.md
```
Sama seperti Jekyll, Hugo menggunakan markdown untuk formatting, setelah selesai menulis, untuk melihat hasilnya
```shell
$ hugo server
```
Perintah itu akan membuat server hugo aktif dan siap untuk menerima request.

Selanjutnya, akan dibahas mengenai deployment ke [Netlify.com](https://netlify.com).
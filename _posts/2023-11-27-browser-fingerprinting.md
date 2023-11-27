---
layout: post
title: "Browser fingerprinting, bagaimana tracker memata-matai pengguna"
date: 2023-11-27
published: true
tags:
  - development
  - security
  - privacy

category: today
---

Browser yang digunakan oleh kita, ketika mengakses suatu website, website tersebut bisa melakukan tracking terhadap kita, yang mana yang melakukan tracking itu memiliki profile kita, device yang kita gunakan, dari mulai sistem operasi, jenis browser, hingga extension, resolusi yang digunakan.

Dan data kita bisa dijual ke pihak lain oleh perusahaan tracker tersebut.

Hal ini menjadikan kita selaku pengguna akan dimata-matai, kemanapun kita melakukan browsing, akan bisa dikenali bahwa Deden telah mengakses ini itu, dan bisa dibuatkan profile dan juga korelasi dengan teman, keluarga dan lainnya.

Untuk mengecek apakah kita rentan untuk diikuti oleh tracker-tracker tersebut, bisa menggunakan [tool yang dibuat oleh EFF](https://coveryourtracks.eff.org/), dengan tool ini, kita bisa tahu apa saja yang rentan, misalkan untuk browser Safari yang saya gunakan

![](/images/posts/browser-open.png)

Ada beberapa browser yang secara default melakukan perlindungan privacy, salah satunya [browser Brave](https://brave.com/). Untuk browser yang tidak menyediakan fitur ini secara default, kita bisa melakukan proteksi lain, yaitu dengan DoH (DNS over HTTPS Protocol), dan untuk kasus DoH provider yang saya gunakan, memiliki proteksi terhadap iklan dan tracker, [saya menggunakan DoH TiarApp](/2019/09/menjaga-privasi-dan-keamanan-dalam-berinternet).

Setelah melakukan setting dan menggunakan DoH Tiar App, hasil dari Cover Your Track EFF mejadi begini.

![](/images/posts/browser-protected.png)

Proteksi terhadap tracker ini sangat penting, karena sangat intrusif, karena kita tidak hanya akan diikuti di browser, tapi aplikasi-aplikasi diluar browser, seperti kita akan mendapatkan iklan di aplikasi Instagram, Twitter, TikTok, dan lainnya.

Karena sidik jari device yang kita gunakan sudah dimiliki oleh tracker, jadi gampang untuk mereka untuk bisa menampilkan iklan yang cocok untuk kita, karena sudah mempelajari kebiasaan kita ketika browsing menggunakan browser atau ketika scrolling instagram dan aplikasi lainnya, karena semua di ekosistem yang sama, dengan tracker yang masing-masing saling melengkapi satu sama lain.

#### Kita rekap ya,
1. Gunakan browser yang secara default melindungi pengguna, coba menggunakan [Firefox](http://firefox.com/) atau [Brave](https://brave.com/)
2. Jika hendak menggunakan proteksi, gunakan DoH/DoT, yang saya menggunakan [https://doh.tiar.app/](https://doh.tiar.app/)
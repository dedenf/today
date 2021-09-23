---
layout: post
title: "Mengubah dan mendapatkan format rsa untuk ssh dari openssh private"
date: 2021-09-23
published: true
tags:
  - development
  - writing

category: today
---

Saya mendapatkan file yang berisi private key dari openssh, yang mana itu bisa digunakan untuk login ke server, tetapi terkadang SSH client yang digunakan lebih banyak support format dari RSA, biasanya file openssh private ini memiliki format sebagai berikut,

```shell
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAAB....
-----END OPENSSH PRIVATE KEY-----
```

File ini merupakan file dari OpenSSH private key, kita perlu melakukan konversi ke dalam format `rsa`.

Untuk melakukan konversi, diperlukan aplikasi `puttygen` untuk mengubah format dari Openssh ke format `rsa` dengan perintah

```shell
puttygen opensshprivate-key -O private-sshcom -o mykey-converted
```

Dari sini, konversi dilakukan, dan mengubah file tersebut menjadi format SSH2, biasanya dengan bentuk file seperti ini,

```shell
---- BEGIN SSH2 ENCRYPTED PRIVATE KEY ----
Comment: "user@server-app"
P2/56wAABa4AAA....
---- END SSH2 ENCRYPTED PRIVATE KEY ----
```

Setelah konversi ke format SSH2, bisa lebih mudah untuk melakukan konversi ke RSA, pertama, kita lakukan konversi private key ini dulu ke RSA private key

```shell
ssh-keygen -i -f mykey-converted > id_rsa-mykey
```

dan memiliki format seperti berikut,

```shell
-----BEGIN RSA PRIVATE KEY-----
MIIG5AIBAAKCAYEA....
-----END RSA PRIVATE KEY-----
```

Dan karena kita sudah memiliki private key dalam format RSA, maka kita bisa mengenerate RSA public key dari private key yang sudah kita punya ini dengan perintah,

```shell
ssh-keygen -y -f id_rsa-mykey > id_rsa-mykey.pub
```

Dimana `-y` adalah paramater yang digunakan untuk input key file private key yang kita punya, dan `-f` adalah path ke file yang dimaksud, kemudian `>` bentuk redireksi ke dalam output file yang dimaksud, di sini saya gunakan nama file `id_rsa-mykey.pub` untuk file hasil generate tersebut.

Setelah mendapatkan file public key, bisa langsung digunakan untuk login (dengan private key didalam folder yang sama), saya biasanya copy file tersebut ke folder `~/.ssh/`, yang mana bisa langsung digunakan ketika mau login, tinggal gunakan `-i ~/.ssh/id_rsa-newkey` atau melakukan `ssh-add ~/.ssh/id_rsa-newkey`.

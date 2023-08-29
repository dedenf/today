---
layout: post
title: "Bermain docker dan MySQL lagi"
date: 2023-08-29
published: true
tags:
  - development
  - writing

category: today
---

Karena ada kebutuhan untuk load data saham, yang berisi broker summary dan informasi di dalamnya, meski berformat `.csv` tapi memang bisa diimport ke dalam database, di sini saya menggunakan MySQL sebagai engine database, dan juga, karena tidak mau 'mengotori' instalasi macOS saya, maka saya menggunakan docker image sebagai media untuk bisa menggunakan MySQL.

Karena saya menggunakan Macbook Pro dengan chip M1, Apple silicon, yang memiliki arsitektur ARM, jadi menggunakan container image yang memang dibuat khusus untuk arsitektur ARM ini.

Seperti biasa, menggunakan `docker pull arm64v8/mysql`, perintah ini akan melakukan pull/download container image tersebut ke local registry.

Di sini tidak akan ada setup yang aneh-aneh, hanya ingin lakukan instalasi dan load data yang ada.

Kemudian jalankan docker image tersebut, `docker run --name=market-data -p 3307:3306 -h 0.0.0.0 -e MYSQL_ROOT_PASSWORD=kosonginaja -d arm64v8/mysql`, dengan melakukan itu, kita menjalankan container dan melakukan binding terhadap host komputer lokal kita dengan port forward 3307 yang merujuk ke port 3306 yang ada di image MySQL tersebut.

Kemudian login ke MySQL menggunakan mysql client, di macOS saya install dulu dengan `brew install mysql-client`, yang mana akan instalasi mysql client untuk konek ke box mysql docker tadi.

```
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 46
Server version: 8.1.0 MySQL Community Server - GPL

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>
```

Perlu beberapa saat untuk memakai lagi topi DBA zaman dulu, dan happy data explore!
---
layout: post
title: "Today: 31 Maret, 2021, midday record"
date: 2021-03-31
published: true
tags:
  - development
  - writing
  - updates
  - notes
  - tech
category: today
---

### Menggabungkan 2 TXT SPF record

Hal baru yang dipelajari ketika melakukan konfigurasi domain untuk keperluan mail provider, saat ini sedang menggunakan satu provider, dan kemudian ada keperluan untuk mengkonfigurasikan `spf1`, karena sudah ada konfigurasi sebelumnya juga, dalam bentuk `TXT `record, jadi diharuskan untuk dilakukan merging, untuk melakukan merging, bisa dilakukan,

Misalkan kita memiliki 2 `TXT` record untuk setting `spf` seperti di bawah ini, 

`v=spf1 include:spf.protection.outlook.com -all`

`v=spf1 include:email-messaging.com ~all`

Dikarena kan dalam satu domain record, hanya boleh ada satu `spf1` dan hanya boleh satu `-all`, maka 2 record tersebut digabungkan, menjadi

`v=spf1 include:spf.protection.outlook.com include:email-messaging.com -all`


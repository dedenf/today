---
layout: post
title: "Belajar menggunakan Podman sebagai pengganti Docker untuk container management"
date: 2023-09-05
published: true
tags:
  - development
  - writing

category: today
---

Menggunakan Docker memang menyenangkan, seperti pada postngan sebelumnya, saya bermain lagi dengan docker, tetapi yang saya tidak suka adalah, untuk yang menggunakan docker instalasi secara default, di sini saya ambil contoh di sistem macOS, setidaknya harus ada beberapa setting yang harus dilakukan agar docker bisa berjalan tidak dalam posisi `root`.

Dengan menggunakan docker, dengan setting [konfigurasi rootless](https://docs.docker.com/engine/security/rootless/) bisa saja, tapi males banget untuk setting ini itu, dan terlalu ribet.

### Podman
Kemudian saya kenal [Podman](https://podman.io), bisa instalasi dengan menggunakan `homebrew` untuk macOS, untuk system operasi lain, silakan refer ke dokumentasinya.

Cukup *straight forward* instalasinya, dan untuk yang ingin menggunakan aplikasi desktop, seperti docker desktop, bisa juga, bisa liat-liat di [Podman Desktop](https://podman-desktop.io/d), dan iya, bisa install aplikasi ini dengan menggunakan `homebrew`.

#### Pull/Push
Podman memiliki perintah yang mirip dengan docker command umumnya, seperti `run`, `exec` dan lainnya, hal ini tentunya sangat berguna untuk yang sangat bergantung pada docker, proses perpindahan juga lebih mudah.

Untuk sumber container images, podman bisa mengambil dari [docker](https://docker.io/), [quay](https://quay.io/), [ghcr](https://ghcr.io), [gcr](https://cloud.google.com/artifact-registry).

```bash
~ on ☁️  deden.fathurahman@aladinbank.id took 2s
❯ podman search waypoint
NAME                                            DESCRIPTION
docker.io/hashicorp/waypoint-odr                The image Waypoint uses for on-demand runner...
docker.io/hashicorp/waypoint                    A tool to build, deploy, and release any app...
docker.io/dockette/hashicorp                    Dockette image with preinstalled Nomad, Cons...
...
```

Dengan menggunakan perintah `podman search <query>` akan mencari image yang dimaksud di repo registry yang ada, atau bisa juga denga nmenggunakan aplikasi desktop podman, dengan fungsi yang sama, hanya saja dengan UI desktop.

![podman desktop](/images/posts/podman-desktop-pull.png)

Ada beberapa fungsi yang bisa digunakan di aplikasi desktop tersebut, dan mungkin lebih mudah melihat podman beraksi secara visual.

#### RUN! FORREST RUN!

Untuk menjalankan container, perintah sangat mirip dengan docker, 
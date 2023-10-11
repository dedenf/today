---
layout: post
title: "Playing with Canonical Multipass"
date: 2023-10-11
published: true
tags:
  - development
  - linux

category: today
---

Recently i'm looking for a solution to deploy a small kubernetes (k8s) cluster, with minimum requirements, easy to use, easy to provision, came across few options like rancher, okd, minikube, kind, and microk8s.

Of cource, i installed all of it!

And now using microk8s and kind for kubernetes development, a bit too much, but i'm interested with the technology, so i want to dig deeper to get the sense of the tools.

While provisioning mickrok8s, which is a product from Canonical, the company behind Ubuntu Linux distribution, it use a program called [Multipass](https://multipass.run/), this is interesting, a program to provision instances.

Multipass reminding me a lot to Vagrant, it can search publicly available images (Ubuntu based of course), the program distributed to Windows, Linux, macOS, so i want to dig deeper with this Multipass.

Since i'm using macOS, obviously installing it using `homebrew`, after that, we can call and execute the app from the terminal to get a better view what it's capable of.

So let's try a basic command to get used with this application.

Launching instance
To launch an instance, execute this command `multipass launch`, it will launch a default option configuration, if you wanted to use a custom spec, you can call it with option, `multipass -m 4G -n server-satu`, this will create an instance with 4GB of RAM dan a host with `server-satu` name, quite easy right?.

Or we can get creative with custom memory, cpu, and disk, like using this command `multipass launch -m 4G -c 2 -d 20G -n server-satu`, as you might guess, it will spin with 2 CPU, and 20G disk space, if you did not specity the name or alias of the instance, multipass will generate one for you, randomly.

Other operation
We can get more sub-command with multipass, like for example `multipass list`, it will displayed a list of instance that we launched

```shell
❯ multipass list
Name                    State             IPv4             Image
primary                 Stopped           --               Ubuntu 22.04 LTS
creative-ant            Stopped           --               Ubuntu 22.04 LTS
micro2                  Stopped           --               Ubuntu 22.04 LTS
microk8s-vm             Stopped           --               Ubuntu 22.04 LTS
```

Other command like `delete`, `alias`, `info` are some of many other command used on `Multipass`, the instance will took your space, and interestingly, that instances, you can either mount it or unmount it however you like, if it's mounted, it will be displayed on your `Multipass list` command result, and if you wanted to mount other people's image, you can, just find it using `Multipass find`, and it will displayed other image that other people already published (just be careful), and using Multipass it's just like using `docker` or `podman` commannd.

So right now, even thought i'm using UTM that uses Qemu for install an instance, but using Multipass is quite handy, and fast. I'm using UTM if i wanted to have another operating system like Windows, macOS, or other Linux distribution, that obviously did not supported by Multipass which only support Ubuntu, but it's find, since i'm doing a lot of experiment using Ubuntu, it helped me a lot.

If you wanted to have a small, easy to use Ubuntu , you can consider Multipass a go.

On the much complex configuration, Multipass can use other virtualization drivers, like virtualbox, or Qemu for instance, using that it can provision other operating system like Windows or macOS, or other OS that suits your need.

Maybe another chance, i'll write about this.
---
author: "Bernardo"
title: "tuntap"
date: 2019-06-16T20:35:10-04:00
tags: ["kernel"]
---

TIL about `tuntap` as a way to create virtual network kernel interfaces. They are
network devices supported entirely in software. While `tun` is used to simulate
a network layer which operates with packets like IP packets, `tap` is used to
simulate a link layer, operating with packets like Ethernet frames. Examples of
applications are `OpenSSH` and `Hamachi`. Example of `tun` usage:

{{< highlight bash >}}
$ sudo ip tuntap add mode tun tun0
$ sudo ip link set tun0 up
$ sudo ip addr add 192.168.1.1/24 dev tun0
{{< /highlight >}}

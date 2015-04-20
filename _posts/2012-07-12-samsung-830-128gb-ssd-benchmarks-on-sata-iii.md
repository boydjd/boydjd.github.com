---
layout: post
title: "Samsung 830 128GB SSD Benchmarks on SATA III"
description: ""
category: 
tags: []
---
{% include JB/setup %}

SSD: Samsung 830 128GB

Model Number: MZ-7PC128D

Firmware: CXM03B1Q

Capacity: 128GB

Filesystem: ext4,noatime,nodiratime,barrier=0,nobh,commit=100,nouser_xattr,data=ordered,discard

Notes: SATA III  

{% highlight bash %}
$ hdparm -Tt /dev/sda

/dev/sda:
 Timing cached reads:   15558 MB in  2.00 seconds = 7783.64 MB/sec
  Timing buffered disk reads: 1458 MB in  3.00 seconds = 485.44 MB/sec

$ dd if=/dev/zero of=tempfile bs=1M count=1024 conv=fdatasync,notrunc
  1024+0 records in
  1024+0 records out
  1073741824 bytes (1.1 GB) copied, 3.83493 s, 280 MB/s

$ echo 3 > /proc/sys/vm/drop_caches
$ dd if=tempfile of=/dev/null bs=1M count=1024
  1024+0 records in
  1024+0 records out
  1073741824 bytes (1.1 GB) copied, 3.19219 s, 336 MB/s
$ dd if=tempfile of=/dev/null bs=1M count=1024
  1024+0 records in
  1024+0 records out
  1073741824 bytes (1.1 GB) copied, 0.172581 s, 6.2 GB/s
{% endhighlight %}

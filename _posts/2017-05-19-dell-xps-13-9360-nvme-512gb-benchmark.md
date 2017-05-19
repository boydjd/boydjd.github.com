---
layout: post
title: "Dell XPS 13 9360 NVMe 512GB Benchmark"
description: ""
category: 
tags: []
---
{% include JB/setup %}

NVMe 512GB

Capacity: 512GB

Filesystem:  ext4 (rw,relatime,errors=remount-ro,data=ordered)


{% highlight bash %}
# hdparm -Tt /dev/nvme0n1

/dev/nvme0n1:
 Timing cached reads:   16658 MB in  2.00 seconds = 8345.91 MB/sec
 Timing buffered disk reads: 3364 MB in  3.00 seconds = 1120.94 MB/sec
# dd if=/dev/zero of=tempfile bs=1M count=1024 conv=fdatasync,notrunc
1024+0 records in
1024+0 records out
1073741824 bytes (1.1 GB, 1.0 GiB) copied, 2.84115 s, 378 MB/s
# echo 3 > /proc/sys/vm/drop_caches
# dd if=tempfile of=/dev/null bs=1M count=1024
1024+0 records in
1024+0 records out
1073741824 bytes (1.1 GB, 1.0 GiB) copied, 0.98266 s, 1.1 GB/s
# dd if=tempfile of=/dev/null bs=1M count=1024
1024+0 records in
1024+0 records out
1073741824 bytes (1.1 GB, 1.0 GiB) copied, 0.170305 s, 6.3 GB/s
{% endhighlight %}

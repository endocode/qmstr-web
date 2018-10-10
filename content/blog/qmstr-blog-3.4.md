+++
title = "Quartermaster Sprint 3.4 Update: ccache, partial linking and more"
date = "2018-09-25T00:00:00+01:00"
tags = ["qmstr", "FOSS", "compliance", "update"]
categories = ["qmstr"]
banner = "img/blog/qmstr-ms-2-report-title.jpg"
+++

We are starting to analyze bigger projects with Quartermaster, like
the [GNU C library](https://www.gnu.org/software/libc/) (glibc). This
is one of the first larger cases of analysis where the resulting
compliance information is relevant for numerous real-life
products. Not only does this reveal a number of corner cases of how
binaries are constructed because the C library is special. It also
takes a lot of time, so combining Quartermaster with technologies that
speed up compilation becomes more important. The key features
Quartermaster learned from this are to work well in combination with
[ccache](https://ccache.samba.org/), and support for partial linking
which is applied in glibc. What these changes mean is explained
below.
<!--more-->

## Overall direction: Real-life cases, functional completeness

This is the report on the fourth sprint of the third Quartermaster
milestone. The sprint ended on September 19. It is part of a larger
push as the key goal for this milestone to implement functionally
complete instrumentation for key projects like
[openssl](https://www.openssl.org/), glibc as mentioned above, or the
[Linux kernel](https://www.kernel.org/). These projects are essential to
many products today, and definitely examples for where compliance is
most relevant. So we hope that these improvements will be useful to
thiose working on deploying Quartermaster in production.

## 

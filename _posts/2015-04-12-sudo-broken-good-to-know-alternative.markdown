---
layout: post
title:  "Sudo Broken? Good To Know Alternative."
date:   2015-04-12 12:00:00
categories: linux
---

Are you on a graphical system where you have sudo access but for some reason or another sudo's broken? Well, what you can do is use gksudo as an alternative as follows.

Before:

    sudo apt-get update

After:

    gksudo "apt-get update"

\(note the quotes... they be required, else you might interfere with gksudo with command line switches.\)

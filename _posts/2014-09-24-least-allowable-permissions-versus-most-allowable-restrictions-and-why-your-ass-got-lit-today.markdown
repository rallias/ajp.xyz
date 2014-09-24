---
layout: post
title:  "Least Allowable Permissions Versus Most Allowable Restrictions and Why Your Ass Got Lit Today"
date:   2014-07-26 21:34:00
categories: security
---

I don't think I'm particularily heinous. I have a security policy that involves restricting who has access to what, beyond the normal I need a password deal. I have a tendency to go all in, do research, and apply more restrictive security policies. Today, that saved my ass.

Lets back up a moment.

What is Least Allowable Permissions? Least Allowable Permissions is the security policy that basically says "they can't access this, so I'm content". This is relatively standard policy. Most people will log in, set a relatively decent password (yeah, I chuckled there), and call it good.

Why is this bad? Well, say a hacker finds a way to remotely execute their line of code on your server without needing your password. Today, we saw an exploit with BASH that when combined with other software, such as OpenSSH daemon, Apache+CGI, et cetera, can act really nasty. I don't mean eew 2g1c, I mean smoldering pit of human flesh.

What do I do that's so radically different? Like I said, I will research software, see what additional security restrictions I can apply to it, and I go ahead and apply said restrictions. Something so simple as Nginx never sees root, nor will it ever have to. IPTables can forward 80 to 8080, Nginx can be launched as the necessary user without any intervention. It can't change users, but that's a good thing. It never has root in the first place.

What else do we have on our list? There's SSH, which I personally replaced with Dropbear and put on a separate vpn. Not just a different port, a different network altogether.

One thing I'm looking into is Docker. It's not a be all end all security solution, but it allows me to layer on additional restrictions to applications. Layers such as "this users data cannot read that users data", "this application runs in a separate namespace to that application", et cetera.

The goal is raising attack costs, and being aware. You gotta watch for this kind of stuff, be aware that there are exploits, and that someone's going to try and break in.

So what should you do? Look into moving your SSH access to VPN. Do an update once in a blue moon. Do your homework, find new security layers, apply them properly.

TL;DR: Do your damn job.

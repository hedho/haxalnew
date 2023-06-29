---
layout: post
title:  "KISSmo Paste"
tags: development
mathjax: on
---

Visit the demo.

[![The Demo](https://i.imgur.com/YzuOQ6T.png)](https://paste.oddprotocol.org)

# KISSmo Paste

This is a simple stupid Pastebin developed for myself and people to use it as a software at my websites!
KISSmo requires no database either mysql or sqlite it simply runs on flat file base.
--------------------------------------------------------------

## Setup

| Things to do | index.php |
| ------ | ------ |
| Search for | **$sitename=""** |
| Search for | **"$ncsite=""** |

Replace respective codes above to represent you're site.

This configuration is needed in order to include fiche at you're build for nginx, apply this changes to you're nginx.conf for you're respective site:

```
    location /p/ {
   alias /home/admin/web/paste.oddprotocol.org/public_html/p/;
   index index.txt;
   autoindex on;
}
```

This configuration is needed for you're OpenHTTPD if you're running OpenBSD, apply this changes on you're httpd.conf for you're respective site:

```
	location "/test/p/*" { 
		directory { auto index, index "index.txt" }
	}
```
KISSmo is fully compatible with Terminal Lynx or other terminal browsers!

[![The Demo](https://i.imgur.com/J5j9icZ.png)](https://paste.oddprotocol.org)

Developed by monaco (C)

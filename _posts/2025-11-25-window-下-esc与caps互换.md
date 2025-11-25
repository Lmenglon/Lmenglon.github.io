---
author: Langle
categories:
- windows
- 快捷键
date: 2025-11-25 16:33:59 +0800
description: Window 下 esc与caps互换
last_modified_at: 2025-02-16 20:13:48 +0800
layout: post
math: true
mermaid: true
title: Window 下 esc与caps互换
---

命名为. reg，执行文件
```sh
Windows Registry Editor Version 5.00
 
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Keyboard Layout]
"Scancode Map"=hex:00,00,00,00,00,00,00,00,03,00,00,00,3a,00,01,00,01,00,3a,00,00,00,00,00
```

还原

```sh
Windows Registry Editor Version 5.00
 
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Keyboard Layout]
"Scancode Map"=-
```
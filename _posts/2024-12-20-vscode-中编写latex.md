---
author: Langle
categories:
- tectonic
- Latex Workshop
- TexLab
date: 2024-12-20 15:17:34 +0800
description: 在vscode中用配置tectonic
layout: post
math: true
mermaid: true
title: Vscode 中编写latex
---

> tectonic+ texlab + latex workshop 相关配置 
> Windows 下配置
{: .prompt-info }

`tectonic` 第一次编译 tex 文件过程中下载依赖，不需要像 texlive 等要提前安装依赖包。

## tectonic
### [下载](https://tectonic-typesetting.github.io/en-US/install.html)
安装目录，`shift+右键` 打开 `PowerSheel`
``` powershell
[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072
iex ((New-Object System.Net.WebClient).DownloadString('https://drop-ps1.fullyjustified.net'))
```

添加当前路径为环境变量

### 测试
```shell
tectonic -V  
## tectonic 0.15.0Tectonic 0.15.0
```

常用命令
```shell
## 构建文档
tectonic -X build

## 编译当个文档
tectonic paper.tex

## 创建新项目
tectonic -X new tex-demo

```

> tectonic 在编译过程中关键字后面要加空格才能顺利编译。
{: .prompt-warning }

```tex
% tex 
{\large阻挡层的宽度}
% ERROR:Undefined control sequence.

{\large 阻挡层的宽度}
```

## TexLab
[texlab](https://github.com/latex-lsp/texlab) 为 latex 提供了语言服务器协议（lsp)，可以看下 [wiki]([Previewing · latex-lsp/texlab Wiki](https://github.com/latex-lsp/texlab/wiki/Previewing#sumatrapdf))，替换 latex workshop 相关配置。

Texlab 只提供编辑提示，编译需要配合其他来实现。例如：`tectonic`

Texlab+ tectonic配置
[Tectonic · latex-lsp/texlab Wiki](https://github.com/latex-lsp/texlab/wiki/tectonic)
```json
{
  "texlab.build.executable": "tectonic",
  "texlab.build.args": [
    "-X",
    "compile",
    "%f",
    "--synctex",
    "--keep-logs",
    "--keep-intermediates"
  ]
}
```

## Latex Workshop

可以将 `Latex Workshop` 的 tools 换成 `tectonic`
官方解决方案：[将 Tectonic 与 VS Code 结合使用 ·构造排版/构造 ·讨论 #896 --- Using Tectonic with VS Code · tectonic-typesetting/tectonic · Discussion #896](https://github.com/tectonic-typesetting/tectonic/discussions/896)

### Tex自动格式化-latexindent

下载链接：[CTAN: Package latexindent](https://ctan.org/pkg/latexindent)

```json
// latex自动格式化

"latex-workshop.formatting.latex": "latexindent",

"latex-workshop.formatting.latexindent.path": "E:\\...\\latexindent\\bin\\windows\\latexindent.exe",
```

参考链接
1. [使用 tectonic 快速入门使用 latex - 编程与开发](https://erasin.wang/latex-quick/)
---
author: pedro
categories:
  - tutorials
cover:
  alt: 500px-logo_-_2010-10-27_-_v23_-_ridgid_-_rgb_-_final
  image: /wp-content/uploads/2018/09/500px-logo_-_2010-10-27_-_v23_-_ridgid_-_rgb_-_final.png
date: "2023-09-24T18:19:52+00:00"
tags:
  - debian
  - linux
title: 'LibreOffice: Spell checking, dictionary, localization et all'

---
![](https://wiki.documentfoundation.org/images/thumb/3/3d/Logo_-_2010-10-27_-_v23_-_RIDGID_-_RGB_-_Final.png/500px-Logo_-_2010-10-27_-_v23_-_RIDGID_-_RGB_-_Final.png)

So in order to install further features to your LibreOffice installation, like spell checking, dictionary, localization and some other features, in a a very easy way, just copy these simple commands. Mind you that the _tag_ after the package name, refers to my personal taste/installation, i.e.: _libreoffice-l10n-pt_ where **pt** is my country localization files. in _myspell-pt-pt_ **pt-pt** is specific to European Portuguese. To get a full list of options and choose your own check the Debian [Package page](https://bit.ly/3fccCk8).

To have a better understanding of your _code_ please check this [link](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes).

```
$ sudo apt install myspell-pt-pt hyphen-pt-pt \
libreoffice-l10n-pt mythes-pt-pt libreoffice-help-pt \
aspell-pt-pt aspell-pt
```

For further info on how to buff up your LibreOffice installation, check [Debian Wiki](https://bit.ly/33ziGxH).

---
title: ubuntu rstudio 한글입력문제 해결하는 방법
author: ''
date: '2020-06-23'
slug: ubuntu-rstudio-한글입력문제-해결하는-방법
categories: []
tags: []
---

 우분투 환경에서 rstudio를 설치하고 코딩간에 한글을 입력할 때 백스테이스를 누르면 '('
문자들이 등장하고 잘못 입력한 글을 지울 수 없어 난감했었는데 오늘 이 문제를 해결해서 
망각하지 않도록 적어놓으려고 합니다.

해결방법은 다음의 주소에서 찾았습니다.

https://support.rstudio.com/hc/en-us/articles/205605748-Using-RStudio-0-99-with-Fctix-on-Linux

이 해결방법은 일본인이 작성한 글을 이용해 적은 것인데 다음의 블로그를 통해 해결
방법을 적어놓았더군요. 전 일본어는 영 몰라서 그냥 참고만 했습니다.

https://blog.goo.ne.jp/ikunya/e/ca6fd08bb8f304ccb90362b7d78b560c


 가장 중요한 부분은 다음의 코드를 우분투 터미널에 입력하는 것인데 본인의 시스템
 아키텍쳐에 따라 `$(dpkg-architecture -qDEB_BUILD_MULTIARCH)` 부분에 들어갈 단어과 `/usr/lib/rstudio/bin/plugins/platforminputcontexts/` 경로가 상이할 수 있습니다.


```code
$ sudo ln -s /usr/lib/$(dpkg-architecture -qDEB_BUILD_MULTIARCH)/qt5/plugins/platforminputcontexts/libfcitxplatforminputcontextplugin.so /usr/lib/rstudio/bin/plugins/platforminputcontexts/
```

 저 같은 경우 Ubuntu 1.04LTS를 사용하는데 최종적으로는 다음과 같이 입력했던니 해결
 되었습니다. 
 
 

```code
sudo ln -s /usr/lib/x86_64-linux-gnu/qt5/plugins/platforminputcontexts/libfcitxplatforminputcontextplugin.so /usr/lib/rstudio/plugins/platforminputcontexts/
```
 


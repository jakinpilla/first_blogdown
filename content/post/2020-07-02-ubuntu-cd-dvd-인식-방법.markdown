---
title: Ubuntu CD/DVD 인식 방법
author: ''
date: '2020-07-02'
slug: ubuntu-cd-dvd-인식-방법
categories: []
tags: []
---
리눅스는 인식한 장치를 /dev 하위에 파일로 만들어 관리하는데 cdrom의 경우 /dev/cdrom으로 인식됩니다.


```code
ls /dev/cdrom                
```

보통 CD/DVD 미디어 장치는 /media/cdrom 에 마운트 시켜줍니다. 그런데 처음 CD/DVD를 우분투에서
마운트 시킬때 이와같은 경로가 없어 cd /media로 이동 후 mkdir cdrom 명령어를 통해
최종 /media/cdrom 경로의 디렉토리를 미리 만들어 주어야 합니다.


mount 명령어를 통해 장치를 원하는 경로에 마운트 시켜줍니다.


```code
mount <장치경로> <마운트 시킬 경로>
```


```code
mount /dev/cdrom /media/cdrom            
```

이렇게 하며 CD/DVD를 인식하게 되어 사용할 수 있게 됩니다.

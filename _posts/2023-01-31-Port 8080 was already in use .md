---
layout: single
title:  "Port 8080 was already in use"
categories: spring
tag: [jpa, blog, spring, java, error]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
author_profiles: false
sidebar:
    nav: "docs"
---  


![스크린샷 2023-02-01 오후 8 33 22](https://user-images.githubusercontent.com/115622936/216042537-19d61615-b3e2-4a0f-a31f-9eb50a08e457.png)

  
### - 8080 포트가 이미 사용중이라 어플리케이션 실행이 안되는 에러 
  

``` JAVA
$ lsof -i tcp:8080
```  

터미널에 해당 명령어를 작성하면 현재 8080포트에서 실행중인 프로세스를 확인할 수 있다  

``` JAVA
$ sudo kill -9 (숫자)
```
  
위의 명령어를 이용해 현재 사용되고 있는 8080 포트를 죽일 수 있다  

![스크린샷 2023-02-01 오후 9 37 17](https://user-images.githubusercontent.com/115622936/216044449-ab1a83b0-099f-46bd-bcbf-73b40f6ee5e9.png)

끼얏호!
에러해결~

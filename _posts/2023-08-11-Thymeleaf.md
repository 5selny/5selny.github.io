---
layout: single
title:  "Thymeleaf"
categories: csshtml
tag: [blog, css, html]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
author_profiles: false
sidebar:
    nav: "docs"
---  

# Thymeleaf 
가공한 데이터를 이용하여 화면을 만드는 방법 
- 미리 정의된 템플릿을 만들고 동적으로 HTML 페이지를 만들어서 클라이언트에 전달하는 방식
- 요청이 올 때마다 서버에서 새로운 HTML 페이지를 만들어 주기 때문에 서버 사이드 렌더링 방식이라고 한다

서버 사이드 템플릿 엔진으로는 ```Thymeleaf```, ```JSP```, ```Groovy```, ```Mustache``` 등이 있다. 
- Thymeleaf 문법을 포함하고 있는 html 파일을 서버 사이드 렌더링을 하지 않고 브라우저에 띄워도 정상적인 화면을 볼 수 있다.
- thymeleaf 의 확장자명은 .html 이며, Thymeleaf 의 문법은 html 태그 안쪽에 속성으로 사용된다.

 ![스크린샷 2023-08-24 오후 8 49 47](https://github.com/5selny/5selny.github.io/assets/115622936/8b96b889-80d6-49ff-9a9e-1171a8016773) 
- ```<html xmlns:th="http://www.thymeleaf.org">``` Thymeleaf 의 문법을 사용하기 위해서 추가

- ```<p th:text="${data}">Hello Thymeleaf!!</p>``` ThymeleafExController 의 model 의 data 라는 key 값에 담아준 값을 출력
- 이때 사용하는 Thymeleaf 의 문법이 "th:text" 이다


 ![스크린샷 2023-08-24 오후 8 41 54](https://github.com/5selny/5selny.github.io/assets/115622936/31ffcc24-574e-4ef8-a26e-4e1ebccf8559) 
-  ```@RequestMapping(value="/thymeleaf")``` 클라이언트의 요청에 대해서 어떤 컨트롤러가 처리할지 매핑하는 어노테이션 
 url에 "/thymeleaf" 경로로 오는 요청을 ThymeleafExController가 처리하도록 함 

- ```model.addAttribute("data", "타임리프 예제입니다.");``` model 객체를 이용해 뷰에 전달한 데이터를 key, value 구조로 넣어준다

- ```return "thymeleafEx/thymeleafEx01";``` templates 폴더를 기준으로 뷰의 위치와 이름(thymeleafEx01.html)을 반환함
 

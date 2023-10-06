---
layout: single
title:  "[Thymeleaf] EL1007E: Property or field 'token' cannot be found on null"
categories: spring
tag: [spring, blog, error]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
author_profiles: false
sidebar:
    nav: "docs"
---

> # [Thymeleaf] EL1007E: Property or field 'token' cannot be found on null

> ### ⚠️ 문제 발생



![스크린샷 2023-10-06 오후 2 37 16](https://github.com/5selny/5selny.github.io/assets/115622936/9b9932ea-f46c-4ef7-bb9b-218543f0c981)
![스크린샷 2023-10-06 오후 2 37 22](https://github.com/5selny/5selny.github.io/assets/115622936/0bd20e9c-fdf5-48d1-bdfa-8243e3cb799a)

메인 페이지에서 로그인을 눌렀을 때, 로그인 화면이 뜨지않고 500에러가 뜸 

> ### 에러메세지
![스크린샷 2023-10-06 오후 2 37 27](https://github.com/5selny/5selny.github.io/assets/115622936/01df39b7-f8df-4058-bfe8-ea6a5c7bd8c4)

property 또는 field 'parameterName' 값이 null 이 될 수 없다는 에러 메세지 

> ### 🛠 문제 해결 

![스크린샷 2023-10-06 오후 2 37 57](https://github.com/5selny/5selny.github.io/assets/115622936/4e9b844b-7dc7-44b1-9a7b-e2b4b95ddd59)
![스크린샷 2023-10-06 오후 2 38 22](https://github.com/5selny/5selny.github.io/assets/115622936/0abcb3cc-5af0-4c3b-b4ce-89844712521f)

```"${_csrf.parameterName}"``` 코드를 ```"${_csrf?.parameterName}"``` 로 변경하여 문제 해결 

?는 if 를 의미하며 null 이 발생할 수 있는 property 또는 field 값에 넣는다 

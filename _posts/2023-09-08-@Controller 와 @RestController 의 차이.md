---
layout: single
title:  "@Controller 와 @RestController 의 차이"
categories: spring
tag: [jpa, blog, spring, java]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
author_profiles: false
sidebar:
    nav: "docs"
---  

스프링 부트 쇼핑몰 프로젝트 with JPA 책으로 공부하면서 앞서 프로젝트를 위해 배웠던 것과는 달라 정리를 해보았다.
그때는 쓰면서도 왜 쓰는지 몰랐던 것들이, 멘토분들이 ```@Controller```와 ```@RestController``` 차이에 대해 알아보라고 해서 간략하게나마 알아보았던 것들이
이번 공부를 통해 직접 코드를 쳐보며 차이를 몸소 느낄 수 있어서 좋았다.


# @Controller 와 @RestController 의 차이 

```@Controller```와 ```@RestController``` 둘 다 Spring에서 Controller를 지정해주기 위한
어노테이션이다. 전통적인 Spring MVC의 Controller인 ```@Controller```와 RESTful 웹 서비스의
Controller인 ```@RestController```의 주요한 차이점은 Response Body가 생성되는 방식이다. 

![image](https://github.com/5selny/5selny.github.io/assets/115622936/43f64702-148e-4eba-9d95-cf536818ea07)

## ```@Controller``` 
- Controller로 View를 반환할 경우

Spring MVC의 Controller인 ```@Controller```는 주로 *View*를 반환하기 위해 사용한다.

![image-2](https://github.com/5selny/5selny.github.io/assets/115622936/3b7972a6-c56e-4e95-b861-243456c52c1d)

- Controller로 Data를 반환할 경우

View 뿐만 아니라 Data(또는 객체)를 반환해야 하는 경우도 있다. 그럴 때에는 데이터를 반환하기 위해
ResponseEntity(HttpStatus + HttpHeaders + HttpBody 형태의 데이터, 한 마디로 Http 응답 메세지)의
Body(Response Body)를 사용해야 하는데, 이 때 ```@ResponseBody```어노테이션을 사용하면 된다.
이를 통해 Controller도 View 뿐만이 아니라 JSON 형태의 데이터도 반환할 수 있다. 

### ```@Controller```와  ```@ResponseBody``` 예제코드

![image-3](https://github.com/5selny/5selny.github.io/assets/115622936/21082c7c-2469-4963-a01f-aaef54e2533f)

```@Controller```는 보통 View를 반환하기는 하지만 위와 같이 ```@ResponseBody```어노테이션을 활용하면
객체를 반환할 수 있다. ```@RequestParam```의 경우 Request Header 안의 파라미터를 Mapping 해주는
어노테이션이다. 

## ```@RestController``` 
![image-4](https://github.com/5selny/5selny.github.io/assets/115622936/c7731cea-6aa9-457b-97e7-93e3324664b0)

```@RestController```어노테이션은 말 그대로 ```@Controller```와 ```@ResponseBody```가 합쳐진
어노테이션이라고 생각하면 된다. ```@Controller```와 다르게 반환하려는 주류는 JSON 형태의 객체 데이터다.
REST API를 개발할 때 주로 사용하며 마찬가지로 ResponseEntity로 감싸서 주로 반환한다. 

- ```@RestController``` 예제코드

![스크린샷 2023-09-07 오후 9 55 50](https://github.com/5selny/5selny.github.io/assets/115622936/223d54a6-4546-496d-8c3b-2d15308aaf71)


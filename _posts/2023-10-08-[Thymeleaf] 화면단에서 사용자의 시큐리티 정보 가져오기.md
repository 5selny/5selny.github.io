---
layout: single
title:  "[Thymeleaf] 화면단에서 사용자의 시큐리티 정보 가져오기"
categories: spring
tag: [spring, blog]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
author_profiles: false
sidebar:
    nav: "docs"
---

># [Thymeleaf] 화면단에서 사용자의 시큐리티 정보 가져오기

Spring Security 인증을 받은 로그인한 사용자의 정보를 타임리프에서 사용하고 싶을 때 사용
  
ex. 
- 로그인 상태라면 '로그아웃'이라는 메뉴가 나나야 로그인 된 상태임을 알 수 있다
  
- 다른 아이디로 로그인하려면 현재 계정으로부터 로그아웃하고 다시 로그인을 해야 한다

- 상품 등록 메뉴의 경우 관리자만 상품을 등록할 수 있도록 노출돼야 한다

>### build.gradle 의존성 추가

```
implementation 'org.springframework.boot:spring-boot-starter-security'

implementation 'org.thymeleaf.extras:thymeleaf-extras-springsecurity6'

```
![스크린샷 2023-10-13 오후 5 49 02](https://github.com/5selny/5selny.github.io/assets/115622936/45fc1f03-705e-4337-815a-2861c090cb04)


>### 사용 방법

네임 스페이스에 추가 

```
xmlns:sec="http://www.thymeleaf.org/extras/spring-security"
```

![스크린샷 2023-10-13 오후 5 51 07](https://github.com/5selny/5selny.github.io/assets/115622936/9b534d13-ef23-488f-b408-866497f82485)

```
sec:authorize="hasAnyAuthority('ROLE_ADMIN')
sec:authorize="isAuthenticated()
sec:authorize="isAnonymous()
```

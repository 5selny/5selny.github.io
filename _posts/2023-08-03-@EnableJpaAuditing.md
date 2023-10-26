---
layout: single
title:  "JpaAuditing"
categories: spring
tag: [blog, spring, jpa]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
author_profiles: false
sidebar:
    nav: "docs"
---  

# @EnableJpaAuditing

객체를 생성하거나 수정할 때 생성자와 Setter 에 LocalDateTime.now() 등 시간을 나타내는 객체를 넣어 생성일자와 수정일자를 관리할 수 있다.
하지만 여러 엔터티에서 이러한 코딩을 매번 하는 것은 단순하고 번거로운 작업이다.
그래서 인스턴스를 생성하거나 수정하는 변화가 있을 시에 이를 감지하여 자동으로 일시를 저장하도록 할 수 있다.

![스크린샷 2023-08-03 오후 4 11 38](https://github.com/5selny/5selny.github.io/assets/115622936/893b3df6-ff89-4650-9c1b-5698e5ed5bfc)


## 1. Main Application 에 @EnableJpaAuditing 어노테이션 추가
   - configuration 어노테이션을 통해 JPA 에서 auditing 을 가능하게 함

## 2. 생성일자, 생성자를 위한 공통 엔티티 생성
   - 객체를 생성하거나 수정할 때 생성자와 Setter 에 LocalDateTime.now() 등 시간을 나타내는 객체를 넣어 생성일자와 수정일자를 관리할 수 있다.
   - 하지만 여러 엔터티에서 이러한 코딩을 매번 하는 것은 단순하고 번거로운 작업이다.
   - 그래서 인스턴스를 생성하거나 수정하는 변화가 있을 시에 이를 감지하여 자동으로 일시를 저장하도록 할 수 있다.
  
  ![스크린샷 2023-08-10 오후 4 20 13](https://github.com/5selny/5selny.github.io/assets/115622936/f205a4ca-aefe-446d-828d-026a3b012389)


  
  - ```@MappedSuperclass``` 어노테이션 추가
    공통 맵핑 정보가 필요할 때 사용하며 부모 클래스에서 선언하고 속성만 상속받아서 사용하고 싶을 때 사용.

 - ```@EntityListeners(AuditingEntityListener.class)```
    JPA Entity 에 이벤트가 발생할 관련 코드를 실행한다.

 - ```@CreatedDate```: 생성 일자를 관리하는 필드에 현재 날짜를 주입하는 작업을 수행
 - ```@Column( updatable = false )```: 생성일자, 생성자에 대한 필드이기 때문에 수정 불가하도록 설정

 ## 3. 엔티티에서 extends 로 상속받기


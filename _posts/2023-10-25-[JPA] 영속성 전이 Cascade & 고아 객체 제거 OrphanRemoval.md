---
layout: single
title:  "[JPA] 영속성 전이 Cascade & 고아 객체 제거 OrphanRemoval"
categories: spring
tag: [jpa, blog, spring]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
author_profiles: false
sidebar:
    nav: "docs"
---  

> # 영속성 전이 Cascad
> ### 자바 ORM 표준 JPA 프로그래밍  

영속성 전이란 엔티티의 상태를 변경할 때 해당 엔티티와 연관된 엔티티의 상태 변화를 전파시키는 옵션.  
이 때 부모는 One 에 해당, 자식은 Many 에 해당. 
(ex. Order 엔티티가 삭제되었을 때 해당 엔티티와 연관되어 있는 OrderItem 엔티티가 함께 삭제)  

> ### CASCADE 종류 & 설명

```
- PERSIST : (저장) 부모 엔티티가 영속화될 때 자식 엔티티도 영속화
- MERGE : (병합) 부모 엔티티가 병합될 때 자식 엔티티도 병합
- REMOVE : (삭제) 부모 엔티티가 삭제될 때 자식 엔티티도 삭제
- REFRESH : 부모 엔티티가 refresh 되면 자식 엔티티도 refresh
- DETACH : 부모 엔티티가 detach 되면 자식 엔티티도 detach 상태로 변경
- ALL : 부모 엔티티의 영속성 상태 변화를 자식 엔티티에 모두 전이
```

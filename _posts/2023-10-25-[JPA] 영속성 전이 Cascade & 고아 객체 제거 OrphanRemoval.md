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

- PERSIST : (저장) 부모 엔티티가 영속화될 때 자식 엔티티도 영속화
- MERGE : (병합) 부모 엔티티가 병합될 때 자식 엔티티도 병합
- REMOVE : (삭제) 부모 엔티티가 삭제될 때 자식 엔티티도 삭제
- REFRESH : 부모 엔티티가 refresh 되면 자식 엔티티도 refresh
- DETACH : 부모 엔티티가 detach 되면 자식 엔티티도 detach 상태로 변경
- ALL : 부모 엔티티의 영속성 상태 변화를 자식 엔티티에 모두 전이


> # 고아 객체 Orphan / OrphanRemoval

JPA 에서는 부모 엔티티와 연관 관계가 끊어진 자식 엔티티를 자동으로 삭제하는 기능을 제공하는데  
이를 고아 객체 제거라 한다.  
Orphanremoval 을 이용하면, 부모 엔티티의 컬렉션에서 자식 엔티티의 참조만 제거하면 자식 엔티티가 자동으로 삭제된다.  

<img width="482" alt="image" src="https://github.com/5selny/5selny.github.io/assets/115622936/fa8260da-4b86-4ead-a9ba-57bf3eb79615">




> # [JPA] cascade = CascadeType.REMOVE 와 @OnDelete(action = onDeleteAction.CASCADE)의 차이

JPA 에 의해 처리되느냐 DDL 에 의해 cascade 가 걸린 테이블이 생겨 DB 단에서 처리되느냐의 차이


전자: JPA 에 의해 외래 키를 찾아가며 참조하는 레코드를 제거   
	👉🏻 JPA 상에서는 참조하고 있는 레코드의 개수만큼 delete 쿼리가 생성  
	👉🏻 자식 엔티티를 삭제하는 쿼리가 먼저 실행 -> 부모 엔티티를 삭제하는 쿼리 실행  

후자: 데이터베이스 자체에서 on delete cascade 제약조건이 걸리게 됨  
	👉🏻 이를 통해 참조하는 레코드가 모두 제거  


Cascade = CASCADE.REMOVE  
 ▪ JPA 레벨에서 작동한다  
 ▪ DDL 생성시 cascade 제약 조건이 생성됨  
 ▪ 참조하고 있는 레코드 수 만큼 delete 쿼리가 나감  
 ▪ 부모 테이블의 자식 컬럼에 걸어야하므로(일반적으@OneToMany(casecade=CASCADE.REMOVE) 양방향 매핑이 아닌 이상 적용하기 어려움  


@OnDelete ( 지양 )   
 ▪ database 에서 직접 처리  
 ▪ *DDL 생성시 cascade 제약 조건이 생성됨  
 ▪ 데이터베이스 자체에서 on delete cascade 제약조건이 걸리게 됨  
 ▪ 따라서 삭제쿼리가 나가지 않음  
 ▪ 단방향 매핑에서도 적용이 가능 - 자식 테이블의 부모 컬럼에 적용하면 됨  


*DDL(Data Definition Language) : 데이터 베이스를 정의하는 언어이며 CREATE, ALTER, DROP, TRUNCATE 를 말한다) 

---
layout: single
title:  "Lombok Annotation"
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


> # Lombok Annotation

 ### ``` @ToString ```
- java.lang 클래스에서 기본적으로 제공하는 메서드이다.
- ToString이 붙은 클래스는 lombok이 toString() 메소드를 생성해준다.
- 기본적으로는 클래스 이름과 각 필드에 대한 값을 출력한다.
- 출력을 원하지 않는 변수에 ```@ToString.Exclude``` 어노테이션을 붙여주면 출력을 제외할 수 있다.
- 부모 클래스에 대해도 toString을 적용시키고자 한다면 부모 클래스에 ```@ToString(callSuper = true)``` 를 적용한다.
  


### ``` @EqualsAndHashCode ```  



### ``` @NoArgsConstructor ```  
- 매개변수가 없는 기본 생성자를 생성한다.
- 만약 불가능 하다면(final 필드 떄문에) 컴파일 에러가 난다.
- 만약 @NoArgsConstructor(force = true)를 사용하면 컴파일 에러를 발생시키는 대신 모든 final 필드는 기본값(0, false, null)로 초기화된다.


### ``` @RequiredArgsConstructor ```  
- 초기화되지 않은 모든 final 필드, @NonNull 필드에 대한 생성자를 생성해주며 의존성을 주입받을 수 있다.
- @NonNull 필드의 경우 null check 구문 또한 생성할 수 있다.

  

### ``` @AllArgsConstructor ```  
- 모든 필드에 대한 생성자를 만들어준다.
- 마찬가지로 의존성을 주입받을 수 있으며, @NonNull 필드에 대한 null check 구문을 생성할 수 있다.

  

### ``` @Builder ```  
- 빌더를 자동으로 작성해준다.






---
> # 지양해야할 어노테이션
### ``` @AllArgsConstructor ``` 
클래스에 존재하는 모든 필드에 대한 생성자를 자동으로 생성 

* 발생할 수 있는 문제 상황

예를 들어, 두 개의 같은 타입 인스턴스 멤버를 선언한 상황에서 개발자가 선언된 인스턴스 멤버의 순서를 바꾸면, 개발자도 인식하지 못하는 사이에 lombok이 생성자의 파라미터 순서를 필드 선언 순서에 따라 변경하게 된다. 이때, IDE가 제공해주는 리팩토링은 전혀 동작하지 않고, 두 필드가 동일 타입이기 때문에 기존 소스에서도 오류가 발생하지 않아 아무런 문제없이 동작하는 것으로 보이지만, 실제로 입력된 값이 바뀌어 들어가는 상황이 발생한다.

### ``` @Data ```  

```@Data``` = ```@RequiredArgsConstructor``` + ```@Getter``` + ```@Setter``` + ```@ToString``` + ```@EqualsAndHashCode```  
각 annotation의 주의사항을 모두 포함한다.  

```@EqualsAndHashCode``` : equals 메소드와 hashcode 메소드를 생성한다.  
예를 들어, 객체를 Set에 저장한 뒤 필드 값을 변경하면 hashCode가 변경되면서 이전에 저장한 객체를 찾을 수 없는 문제가 발생한다.  

```@RequriedArgsConstructor```의 주의사항은 앞에서 거론했다. 
```@Data``` 대신, ```@Getter```, ```@Setter```, ```@ToString```으로 명시하는 것을 권장한다.  

```@NoArgsConstructor```  
파라미터가 없는 생성자를 생성한다.  

* 사용 시 주의 사항
  
필드들이 final로 생성되어 있는 경우에는 필드를 초기화할 수 없기 때문에 생성자를 만들 수 없고 에러가 발생한다. → @NoArgsConstructor(force=true) 옵션을 이용해 final 필드를 강제 초기화 시켜 생성자를 만들 수 있다.
@Nonnull 같이 필드에 제약조건이 설정되어 있는 경우, 추후 초기화를 진행하기 전까지 생성자 내 null-check 로직이 생성되지 않는다.

### ```@Builder```

```@Builder```를 사용하면 객체 생성이 명확해진다. 가급적 클래스 보다는 직접 만든 생성자 혹은 static 객체 생성 메소드에 붙이는 것을 권장한다.
```@Builder```를 붙이면 파라미터 순서가 아닌 이름으로 값을 설정하기 때문에 리팩토링에 유연하게 대응할 수 있고, 필드 순서를 변경해도 문제가 없다.

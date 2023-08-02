### ```@Enumerated``` 
java 의 enum 타입을 엔티티 클래스의 속성으로 사용할 수 있다. 

- ```@Enumerated(EnumType.ORDINAL)```

  순서를 나타내는 숫자를 database 에 저장한다. 따로 지정하지 않으면 설정되는 기본값.
  enum 필드에 상태값이 추가가 되면 enum 서수와 database 서수가 일치하지 않기 때문에 테스트 실패

- ```@Enumerated(EnumType.STRING)```

  enum 의 name 값을 database 에 문자열로 저장한다.
  enum 필드에 상태값이 추가가 되어도 테스트 통과됨(문자열로 저장되기 때문)

---
### 정리
1. @Enumerated를 사용할때는 가급적이면 STRING을 사용한다.
2. 설계가 문제가 없어도 요구사항은 언제든지 변경될 수 있다.
3. ORDINAL은 Database의 숫자로 저장되기 때문에 직관적이지 않다.
  
  


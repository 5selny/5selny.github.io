# @NotNull, @NotBlank @NotEmpty 차이 

- javax.validation.constraints package에 포함된 기능으로 api에서 값을 입력받을 때 validation 체크를 위해 사용되는 어노테이션 

  ```build.gradle 에 validation 추가 

 	implementation 'org.springframework.boot:spring-boot-starter-validation' 

### @NotNull 
null(X), ""(O), " "(O)

---

### @NotEmpty 
null(X), ""(X), " "(O)

---

### @NotBlank 
null(X), ""(X), " "(X) 

---


```""(초기화된 String) / " "(공백)```

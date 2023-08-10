## 쿼리 로그를 확인하고 싶을 때 
1. src/main/resources 디렉토리 아래에 application.yml 파일을 생성한다


![스크린샷 2023-08-10 오후 11 02 06](https://github.com/5selny/5selny.github.io/assets/115622936/3a81abfa-f320-41c0-aec9-2c32765b00db)


2. 아래의 옵션을 추가한다


![스크린샷 2023-08-10 오후 10 58 41](https://github.com/5selny/5selny.github.io/assets/115622936/9e90cef6-1b2d-430c-91f7-892760ccf29e)


3. 실행하면 H2 쿼리 문법의 쿼리 로그를 확인할 수 있다


![스크린샷 2023-08-11 오전 12 02 32](https://github.com/5selny/5selny.github.io/assets/115622936/cb1c4b9a-c675-4db6-be55-96f117dd118c)

sql 포맷 형식으로 보고 싶다면
![스크린샷 2023-08-11 오전 12 03 14](https://github.com/5selny/5selny.github.io/assets/115622936/6d8c0636-496e-4324-b75f-057f2c589376)

```
properties:
      hibernate:
        format_sql: true 를 추가해주자

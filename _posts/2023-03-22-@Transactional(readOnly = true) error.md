![2](https://user-images.githubusercontent.com/115622936/226861022-ad105629-bd37-4913-86fa-e6a22354930d.png)  
  
쪽지 기능 중 한 명이 받은 모든 받은 편지함을 조회하는 메서드 위에 @Transactional(readOnly = true) 를 추가해주었더니  
위와 같이 빨간색으로 뜨며 에러가 발생했다 
  
  
![3](https://user-images.githubusercontent.com/115622936/226860951-a16c9a25-b710-465e-9f18-04546b957dea.png)  
  
- ``` javax.transaction.Transactional ``` 로 import 되어있는 경우 발생하는 에러  


![1](https://user-images.githubusercontent.com/115622936/226862490-7b400a62-5e3a-4b91-a445-8c4b42727a81.png)
  
- ``` org.springframework.transaction.annotation.Transsactional ```로 변경해주면 해결된다  
  

-----------------------------
      
💡 ``` @Transactional(readOnly = true) ```   
@Transactional 을 수행하기 위해 많은 리소스가 사용된다.  
(readOnly = true) 옵션을 사용하여 해당 메서드가 읽기 전용이라는 것을 명시하면  
영속성 컨텍스트의 관리를 받지 않게 된다.  
  
등록, 수정, 삭제 기능이 없는 메서드에서 사용을 추천한다.




<h2> SnippetException </h2> 

MemberController 테스트 코드에서 마주친 SnippetException.  


  
 
![스크린샷 2023-02-22 오후 6 56 40](https://user-images.githubusercontent.com/115622936/220651340-86bc261d-db80-414b-a59b-41988f2e41da.png)  
Org.springframework.restdocs.snippet.SnippetException: Path parameters with the following names were not found in the request: [pageinfo]  
  
Path parameters 에 pageinfo 를 찾을 수 없다는 에러  
분명 Path parameters 에 잘 들어갔는데 도대체 왜 이러는가 한참을 찾아보고 고민했다  
코드를 이래저래 수정하니 

![스크린샷 2023-02-22 오후 3 35 43](https://user-images.githubusercontent.com/115622936/220651383-db76a4ec-d666-4464-94ec-f54c8ead4b8c.png)  
  
Fields with the following paths were not found in the payload: [PageInfo.page, pageInfo.size, pageInfo.totalElements, pageInfo.totalPages]  
새로운 에러 발생. 다음 paths 을 payload 에서 찾을 수 없다고 함  
이것말고도 ~~~ not be documented 문서화 할 수 없다는 에러도 봤다  
에러를 백번쯤 보다보니 쎄하더라..  
  
앞쪽에 포커스를 두고 보다 뒤쪽을 자세히보니 pageinfo.. pageInfo..  차이가 보이는가  
그렇다. 나는 멍청하게도 pageinfo 로 작성해야하는걸 pageInfo 로 작성해두고 왜 에러가 발생하는가 찾고 있었던 것이다  
  
mockMvc.perform( 뒤에 파라메터로 입력값 page 와 값을 적어주고 pageinfo 로 전부 수정하니 테스트 통과..  
에러메세지는 상당히 친절한 것 같다  
![스크린샷 2023-02-22 오후 6 56 10](https://user-images.githubusercontent.com/115622936/220651417-3c72567e-f7bb-43e2-a706-f14d9324e436.png)  
  
나도 복잡한 에러를 만나 멋있게 풀어나가는 블로깅을 하고 싶지만 현재 내 수준에서는 이게 한계다  
이번 프리프로젝트를 통해서 잘하는 사람들은 어떻게 의사소통하는지, 그리고 어떻게 공부해야하는지  
이 2가지만큼은 확실하게 배울 수 있었던 시간이었던 것 같다  
  
너무나도 부족한 실력인걸 알아서 민폐라는 마음에 적극적으로 의견을 내진 못했지만(물론 그만한 실력도 아직)  
배워가는 것도 많으니 이번 경험을 통해서 한단계 성장하리라 믿고 싶다!

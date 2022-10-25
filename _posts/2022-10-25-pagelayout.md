워밍업 단계임에도 불구하고 벌써부터 시간이 부족한 느낌이다.  
오늘은 Page Layout, Flex box, Wire fame 에 대해  
공부했다. 이 중에서 Flex box가 오늘의 키포인트!  
> ## Layout

화면을 나누는 방법  
- 수직분할
- 수평분할  

> ## Flex box  

### 부모박스 요소에 적용해, 자식 박스의 방향과 크기를 결정

* flex-direction 축
```
flex-direction: row, column, row-reverse, column-reverse
```

 * justify-content 좌우
```
justify-content: flex-start, flex-end, center, space-between, space-around, space-evenly
```

 * align-items 상하
```
align-items: flex-start, flex-end, center, baseline, stretch
```

 * flex-wrap 줄바꿈
```
flex-wrap: nowrap(기본값), wrap, wrap-reverse
```

### 자식 요소에 적용해야하는 Flex box 속성
```
flex-grow 늘어남 flex-shrink 줄어듬 flex-basis 기본 크기 : 0, 1, auto;
```

> ### HTML로 웹 앱 구조 잡기

1. 큰 틀에서 영역 나누기
2. 각 영역을 태그로 표시하기

> ### 그 외

오늘 배운 내용 복습 겸, 내일 진행될 페어 프로그래밍에  
짐짝이 되지 않기 위해 예습을 했다.  


<img width="250" alt="스크린샷 2022-10-25 오후 10 12 16" src="https://user-images.githubusercontent.com/115622936/197802383-0b5266b7-354e-4d0a-b605-5f00cbdb7133.png">
twittler 사진에 있는 화면을 그대로 구현해내는 것인데

여지껏 배운 css&html 문법이 다 들어간 것 같다   
오늘 배운 flex box 부터 어려운 선택자 p:nth-child() 등등.  

어찌저찌해서 나름 비슷하게 완성하고  
마지막 박스의 이름, 날짜, 트윗내용 정렬 및 데코만 남아  
저녁먹고 해야지 하고 저장하고 와서 보니 저장이 안돼서 날라갔다..  
부디 내일 기억나기를...  



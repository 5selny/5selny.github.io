오늘의 주제는 HTML(HyperText Markup Language)와 CSS(Cascading Style Sheet).  
8시간 안에 끝내기에는 정말 방대한 양이었다.  
의문점이 꼬리에 꼬리를 물다보니 처음으로 제 시간 안에 학습을 끝마치지 못했다.  
"이런 것도 있어요~" 라고 이해하고 가볍게 넘어가도 되는 부분이지만 그냥 지나치지를 못했다..  
예를 들어 HTML이 Markup 언어인데 그럼 깃허브에서 봤던 Markdown과의 차이점은 무엇인가?  
에서부터 연습문제를 다 풀고 괜히 거기서 더 나아가 이것 저것 추가로 만들다보니 어느덧 5시.  

코츠 크루님도 해줄 이야기가 많으셨던지 15분이나 늦게 수업이 종료되었다.  
나름 재밌었지만 선택자 부분에서 멘붕이 왔다. 형제, 인접, 하위, 가상 클래스 선택자 등등  
설명없이 문제를 통해 처음 접하다보니 그 순간에는 내가 뭘하는건가 싶었다.  
문제를 통해 대충 잡힌 개념을 글 작성 후에 제대로 공부해서 개념화해야겠다.  


> # HTML, CSS, JS

HTML - 뼈대, 구조(Structure) / CSS - 스타일(Presentation) / JS - 상호작용(Interaction)


### < HTML에서 자주 쓰이는 태그들 >
```
<div>, <span>, <img>, <a>, <ul> & <ol>, <input>, <textarea>, <button> 등
```

> ### HTML (Semantic / Non-Semantic)
-------------------


- #### semantic tags

```
<form>, <table>, <main>, <img>, <header>, <nav>, <aside>, <section>, <footer> 등 content의 의미를 명확히 설명한다. 
```
 

- #### non-semantic tags

```
<div>, <span> 등 content에 대하여 어떤 것도 설명하지 않는다.  
```

> ### CSS  
----
- 과거 CLI(Command Line Interface) 이용  
- 현재 UI(User Interface)/UX(User Experience) 중심  

```
body{
        color:red;
        font-size: 30px;
        
       } 
```

순서대로 selector, Declaration block 선언, property 속성명, value 속성값

> ### 선택자
----

- class 선택자(.)
- id 선택자(#)
- 자식 선택자(>)
- 하위 선택자( ) -> 띄워쓰기
- 형제 선택자(+) -> 다음 하나
- 일반 형제 선택자(~) -> 모두
- 모든 요소 선택(*)

### 가상 클래스 선택자  
- hover -> a:hover(마우스 커서가 올라가있는 동안)
- active -> a:active(마우스를 클릭하고 있는 동안)
- focus -> input:focus(포커스되면 선택) 


> ### CSS 박스  
레이아웃과 영역을 나누기 
margin > border > padding > content, 상-우-하-좌 순

---

> ### CSS Display
| Inline        | Block         | Inline-block|
| ------------- |:-------------:| -----------:|
| 줄바꿈 X        | 줄바꿈 ㅇ      | 줄바꿈 ㅇ       |
| 너비, 높이 X  | 너비, 높이 ㅇ   | 너비, 높이 ㅇ     |
| 좌우 간격 ㅇ  |  좌우 간격 ㅇ     |display: 지정필수|  

너비(width), 높이(heigh), 상하좌우(margin),(padding)
     


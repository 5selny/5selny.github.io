---
layout: single
title:  "Thx!Google"
folder: "csshtml"
categories:
  - csshtml
tags: [css, html]

author_profile: true
sidebar:
  nav: "docs"

toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true

date: 2022-10-26
---

오늘은 페어와 함께 HTML, CSS를 이용하여  
화면 구현을 했고 나름 결과물도 만족스러웠다.  
욕심은 났지만 아는 것의 한계랄까..  
더 아는 것이 많았더라면, 익숙했다면 어땠을까  
생각도 했지만 부족함이 있어야 성장도 있으니까!  
몰랐던 것은 배우면 되고 알아가면 된다.  

<img width="359" alt="스크린샷 2022-10-26 오후 11 06 10" src="https://user-images.githubusercontent.com/115622936/198053667-ff5735a3-ca07-411b-9739-83dfda50e1ec.png"><img width="300" alt="스크린샷 2022-10-25 오후 10 12 16" src="https://user-images.githubusercontent.com/115622936/198053697-46f91e03-1b62-41ed-9c5e-f89f93f2d318.png">

- *좌: 초기화면, 우: 만들어야하는 화면*

피드백 시간은 따로 없어서 셀프로 가졌다.  
잘했던 점은 세션을 마무리하면서 크루분께서  
이번 과제의 포인트를 집어주셨는데 그 포인트를  
전부 생각해내고 적용했다는 것이다. 첫째,  
Flex box를 사용하기 위해 HTML에서  
시맨틱 요소(header, main 등)를 사용해  
하나로 묶어주는 것.  

하지만 페어분께 정확하고 명확하게  
설명하지 못했다는 점이 아쉬웠다.  
머리는 아는데 말로 설명하기 어려웠다.  
더군다나 비전공자라서 위축됐음..ㅎ_ㅎ  
다음에는 개념을 확실히 잡아 정확하게  
의미를 전달할 수 있도록 노력해야겠다.  

앞부분은 그럭저럭 쉬웠는데 뒷부분  
트윗 작성자, 시간, 내용을 분리하는 곳에서  
어려움을 맞이했다.  
<img width="300" alt="스크린샷 2022-10-27 오전 12 33 16" src="https://user-images.githubusercontent.com/115622936/198071701-259462b8-0b5e-432c-b850-8c34c5aabf54.png">


바로 이 시간데이터를 작성자와 같은 라인에 두는 것!  
flex box도 먹히지 않았고, 페어분께서는 너비값을 주어  
화면상으로는 이동이 됐는데 화면을 줄이거나 늘리니  
소용이 없었다. 구글의 힘을 빌려 검색해보다가  
position을 absolute로 주는 방법을 찾게 되었다.  
역시 구글 👍  

대신 부모요소에 relative를 넣어주어야한다는 점은  
놓쳐버렸다는 게 아쉬웠다. 왜 relative가 없는데도  
absolute가 적용됐는가? 찾아보고 또 배웠다.  
HTML의 body 태그는 자체적으로 부모속성인  
relative 값을 갖는다는 점!

여유롭게 완성하고 미적으로 조금 아쉬운 부분만 수정했다.  
<img width="300" alt="스크린샷 2022-10-27 오전 12 36 00" src="https://user-images.githubusercontent.com/115622936/198070955-ed601f45-4974-49c8-88b5-f4cab7a6541a.png">

 
 완성했다는 것에 의의를 둔 결과물..ㅎ  
 하지만 아직도 풀리지 않는 미스테리가 있다.  
 버튼 안에 이미지와 글자가 같이 들어가있는데  
 아무리봐도 동일선상에 있지 않다.  
 동일선상에 두려면 어떻게 해야하는지 조금 더  
 찾아보고 고민해봐야겠다!

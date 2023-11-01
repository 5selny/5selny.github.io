---
layout: single
title:  "cannot resolve placeholder"
categories: spring
tag: [jpa, blog, spring, java, error]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
author_profiles: false
sidebar:
    nav: "docs"
---  




![스크린샷 2023-01-20 오후 5 30 58](https://user-images.githubusercontent.com/115622936/213657817-3be24821-7a95-42e0-8e75-c644a8dacf98.png)
![스크린샷 2023-01-20 오후 4 25 14](https://user-images.githubusercontent.com/115622936/213657828-fdc160eb-27b1-4f3b-a3e8-5c5c17452eb2.png)
풀리지않은 미스테리

터미널에서 .zshrc_profile 에 export로 환경변수에 키값을 담아 저장시켜주었는데도 계속 에러가 해결되지 않았다  
env를 입력했을 때 정상적으로 뜨는 것도 확인이 되는데 왜 인텔리제이에서는 해당 값을 읽어오지 못하는 걸까?  

다음 날 뭐가 됐던 애플리케이션은 실행이 되어야하기 때문에 다시 시도를 했다  
sudo vi ~/.bash_profile 에 키값을 저장하고 source ~/.bash_profile 로 저장  
다시 인텔리제이로 돌아와서 애플리케이션을 실행하니 어제는 아무리해도 돌아가지 않던 애플리케이션이 정상작동했다!!   
도대체 이유가 뭘까? 단지 바뀐건 쉘인데 이 차이가 맞는걸까?   
아직 쉘의 개념도 정확하게 잡힌게 아니라 쉘의 차이는 아닐 것 같다는게 현재의 생각인데  
학습을 마저 마무리하고 추후 깊게 공부해봐야겠다!

> <H2> Controller Slice Test
> <H5> patchMemberTest, getMembersTest, deleteMember
  
<img src="https://user-images.githubusercontent.com/115622936/210552263-bc2d16b7-e838-432e-80ce-6e85a53f0a3a.png" width = 80% height=30%></img>  
테스트 통과가 완료된 patchMemberTest code

<img src="https://user-images.githubusercontent.com/115622936/210552195-aa0620ce-61fb-4eab-a297-04b3827c4ae6.png"></img>

가장 처음 맞이한 에러  
200번이 떠야하는데 404가 뜬다!  
* URL 주소 스펠링 확인  

확인해보니 중간에 mockMvc.perform 과정에서 patch uri 에 '/'가 빠졌던 것  

![스크린샷 2023-01-04 오후 9 01 07](https://user-images.githubusercontent.com/115622936/210552181-967b5b39-6af4-4d82-a88a-41fa24fd8295.png)  
수정하고자하는 파라미터를 제외하고 null 값을 줘도 된다는 점! 

  
<img src="https://user-images.githubusercontent.com/115622936/210552168-63093de2-d5c0-4f9f-914a-09308292931c.png"></img>  
검증 시, 수정된 값만 적어도 된다.



  



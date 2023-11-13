---
layout: single
title:  "multipartFile"
categories: java
tag: [java, blog]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
author_profiles: false
sidebar:
    nav: "docs"
---  


# multipartFile

### Multipart 란?

- 웹 클라이언트가 요청을 보낼 때, http 프로토콜의 바디 부분에 데이터를 여러 부분으로 나눠서 보내는 것
- 웹 클라이언트가 서버에게 파일을 업로드할 때, http 프로토콜의 바디 부분에 파일 정보를 담아서 전송을 하는데 파일을 한번에 여러개 전송을 하면 body 부분에 파일이 여러개의 부분으로 연결되어 전송. 이렇게 여러 부분으로 나뉘어서 전송되는 것을 Multipart data 라고 함.
- 보통 파일을 전송할 때 사용


### Multipart/form-data 란?

- 일반적으로 폼 데이터를 전송하면 application/x-www-form-urlencoded 의 형식으로 전송됨
  - HTTP body 에 바로 전송하고자 하는 데이터가 들어가는 형태
  - 예시) name=lim&age=25 과 같은 key-value 쌍이 body 에 들어가는 것
  - 이렇게 동일한 타입의 문자 데이트를 전송하는 것은 전혀 무리가 없다
- key-value 형태의 문자 데이터와 바이너리 형태의 파일 데이터가 함께 전송되는 것은 다르다
    - application/x-www-form-urlencoded 타입으로는 전송이 어렵다
    - 여기서 multipart/form-data 로 지정되고 정해진 형식에 따라 메세지를 인코딩해 전송한다
    - 이를 처리하기 위해 서버는 멀티파트 메세지에 대해서 각 파트별로 분리하여 개별 파일의 정보를 얻게 된다
    - 이미지 파일도 문자로 이루어져 있어 HTTP request body 에 담아 서버로 전송한다
 

### MultipartFile 이란?
- 사용자가 업로드한 file 을 핸들러에서 손쉽게 다룰 수 있게 도와주는 매개변수 중 하나이다
- 매개변수를 사용하기 위해서는 MultipartResolver Bean 이 등록되어 있어야 한다
- springBoot 에서는 자동 등록을 지원, springMVC 에서는 기본으로 등록해주지 않으므로 꼭 확인해야 한다
  - MultipartFile 인터페이스는 스프링에서 업로드한 파일을 표현할 때 사용되는 인터페이스이다
  - MultipartFile 인터페이스를 이용해서 업로드한 파일의 이름, 실제 데이터, 파일 크기 등을 구할 수 있다


|메소드|설명| 
| ------------- |:-------------:| 
|String getName()|파라미터 이름을 구함| 
|String getOriginalFilename()|업로드한 파일의 이름을 구함| 
|String isEmpty()|업로드한 파일이 존재하지 않는 경우 true를 리턴함|
|long getSize()|업로드한 파일 크기를 구함|
|byte[] getBytes() throws IOException|업로드한 파일 데이터를 구함|
|InputStream getInputStream() throws IOException|업로드한 파일 데이터를 읽어오는 InputStrea을 구함. InputStream의 사용이 끝나면 알맞게 종료해주어야 함|
|void transfer To(File dest) throws IOException|업로드한 파일 데이터를 지정한 파일에 저장함|

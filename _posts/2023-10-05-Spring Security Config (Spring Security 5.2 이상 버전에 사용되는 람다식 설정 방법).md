---
layout: single
title:  "Spring Security Config (Spring Security 5.2 이상 버전에 사용되는 람다식 설정 방법)"
categories: spring
tag: [spring, blog, error]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
author_profiles: false
sidebar:
    nav: "docs"
---


># Spring Security Config
>### 이전 버전에서 설정했던 스프링 시큐리티 설정을 사용할 수 없다?

![스크린샷 2023-10-05 오후 8 14 24](https://github.com/5selny/5selny.github.io/assets/115622936/cfb4709e-af6e-4b59-b905-8c879027a03c)

이전 버전에서 스프링 시큐리티 설정을 위해 사용했던 코드들이 더이상 사용되지 않음(headers 를 포함해 csrf 와 sessionManagement 설정 등).  


스프링 시큐리티 5.2 이상 버전에서 사용되는 람다식 http security 설정 방법은 다음과 같다. 

>### Spring Security 5.2 이상 버전에 사용되는 람다식 설정 방법


```java
@Configuration
@EnableWebSecurity
public class SecurityConfig {

    @Bean
    public SecurityFilterChain filterChain(HttpSecurity http) throws Exception {
        http
            .authorizeHttpRequests(authorize -> authorize
                .requestMatchers("/blog/**").permitAll()
                .anyRequest().authenticated()
            )
            .formLogin(formLogin -> formLogin
                .loginPage("/login")
                .permitAll()
            )
            .rememberMe(Customizer.withDefaults());

        return http.build();
    }
}
```

>### 이전에 사용되었던 설정 방법

```java
@Configuration
@EnableWebSecurity
public class SecurityConfig {

    @Bean
    public SecurityFilterChain filterChain(HttpSecurity http) throws Exception {
        http
            .authorizeHttpRequests()
                .requestMatchers("/blog/**").permitAll()
                .anyRequest().authenticated()
                .and()
            .formLogin()
                .loginPage("/login")
                .permitAll()
                .and()
            .rememberMe();

        return http.build();
    }
}
```

Lambda DSL은 Spring Security를 설정하는데 선호되는 방법이다. 이전 스타일은 최신 Spring Security 7 버전에 사용할 수 없다. 



>### Lambda DSL 방법이 선호되는 이유

- 이전 방식은 반환 타입이 무엇인지 알지 못한 채로 어떤 object 가 설정되는지 명확하지 않다. 깊이 들어갈수록 더 혼란스러워질 수 있다. 경험이 많은 사용자도 자신의 설정이 한가지 작업을 수행하고 있다고 생각한다. 실제로는 다른 작업을 수행하고 있는데 말이다.
- Consistency. 많은 코드 베이스가 두 스타일 사이를 전환하면서 설정을 이해하기 어렵고 종종 잘못된 설정으로 이어졌다.


>### 수정코드

전
![스크린샷 2023-10-05 오후 8 16 47](https://github.com/5selny/5selny.github.io/assets/115622936/d83aea81-2e5a-4563-890e-e2e330601471) 


👇🏻참고 

[spring security reference](https://docs.spring.io/spring-security/reference/migration-7/configuration.html#_use_the_lambda_dsl)

후

![스크린샷 2023-10-05 오후 11 15 16](https://github.com/5selny/5selny.github.io/assets/115622936/480db4be-f28a-41a0-a5e0-998d814af1cc)


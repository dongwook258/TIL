* 스프링 시큐리티
```
1. 사용자의 요청이 서버로 들어옵니다.

2. Authotication Filter가 요청을 가로채고 Authotication Manger로 요청을 위임합니다.

3. Authotication Manager는 등록된 Authotication Provider를 조회하며 인증을 요구합니다. 

4. Authotication Provider가 실제 데이터를 조회하여 UserDetails 결과를 돌려줍니다.

5. 결과는 SecurityContextHolder에 저장이 되어 저장된 유저정보를 Spring Controller에서 사용할 수 있게 됩니다.
```
![image](https://github.com/user-attachments/assets/855384ae-3578-4fe3-9f3b-25766d144cfc)

* Spring Security가 작동하는 내부 구조
```
1. 사용자가 자격 증명 정보를 제출하면, AbstractAuthenticationProcessingFilter가 Authentication 객체를 생성합니다.

2. Authentication 객체가 AuthenticationManager에게 전달됩니다.

3. 인증에 실패하면, 로그인 된 유저정보가 저장된 SecurityContextHolder의 값이 지워지고 RememberMeService.joinFail()이 실행됩니다.
그리고 AuthenticationFailureHandler가 실행됩니다.

4. 인증에 성공하면, SessionAuthenticationStrategy가 새로운 로그인이 되었음을 알리고, Authentication 이 SecurityContextHolder에 저장됩니다
이후에 SecurityContextPersistenceFilter가 SecurityContext를 HttpSession에 저장하면서 로그인 세션 정보가 저장됩니다.


그 뒤로 RememberMeServices.loginSuccess()가 실행됩니다. ApplicationEventPublisher가 InteractiveAuthenticationSuccessEvent를 발생시키고
AuthenticationSuccessHandler 가 실행됩니다.
```
![image](https://github.com/user-attachments/assets/18748211-1a18-44e9-a07e-edc5e536b077)

* 스프링 시큐리티
```
1. 사용자의 요청이 서버로 들어옵니다.

2. Authotication Filter가 요청을 가로채고 Authotication Manger로 요청을 위임합니다.

3. Authotication Manager는 등록된 Authotication Provider를 조회하며 인증을 요구합니다. 

4. Authotication Provider가 실제 데이터를 조회하여 UserDetails 결과를 돌려줍니다.

5. 결과는 SecurityContextHolder에 저장이 되어 저장된 유저정보를 Spring Controller에서 사용할 수 있게 됩니다.
```
![image](https://github.com/user-attachments/assets/855384ae-3578-4fe3-9f3b-25766d144cfc)

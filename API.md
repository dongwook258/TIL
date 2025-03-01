* REST
```
HTTP URI(Uniform Resource Identifier)를 통해 자원(Resource)을 명시하고,
HTTP Method(POST, GET, PUT, DELETE, PATCH 등)를 통해
해당 자원(URI)에 대한 CRUD Operation을 적용하는 것을 의미합니다.
```

* REST 특징
```
Server-Client(서버-클라이언트 구조)
Stateless(무상태)
Cacheable(캐시 처리 가능)
Layered System(계층화)
Uniform Interface(인터페이스 일관성)
```

* REST API 설계 규칙
```
1. URI는 동사보다는 명사를, 대문자보다는 소문자를 사용하여야 한다.

Bad Example http://khj93.com/Running/
Good Example  http://khj93.com/run/  
 

2. 마지막에 슬래시 (/)를 포함하지 않는다.

Bad Example http://khj93.com/test/  
Good Example  http://khj93.com/test
 

3. 언더바 대신 하이폰을 사용한다.

Bad Example http://khj93.com/test_blog
Good Example  http://khj93.com/test-blog  
 

4. 파일확장자는 URI에 포함하지 않는다.

Bad Example http://khj93.com/photo.jpg  
Good Example  http://khj93.com/photo  
 

5. 행위를 포함하지 않는다.

Bad Example http://khj93.com/delete-post/1  
Good Example  http://khj93.com/post/1  
```

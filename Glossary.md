* SQL(RDMS) vs NoSQL
```
SQL : 관계형 데이터베이스 (MySQL)
NoSQL : 관계형 데이터베이스 (MongoDB)
```

* CI / CD
```
CI : 지속적인 통합(Continuous Integration)
CD : 지속적인 제공(Continuous Delivery) [수동] / 지속적인 배포(Continuous Deployment) [자동] 
```

* 컴파일 / 링크 / 빌드
```
test.c -> test.class -> test.exe
      컴파일       링크(링커가 라이브러리등을 연결)
빌드 = 컴파일 + 링크 한 파일들을 실행 가능한(exe) 파일로 만드는 과정
```

* Container
```
한 대의 서버에서 여러 개의 소프트웨어를 안전하고 효율적으로 운영
```

* Docker
```
컨테이너를 관리하기 위한 도구
```
![image](https://github.com/user-attachments/assets/9b18903b-22cb-4c5c-8652-f52a419100b3)
* Kubernetes
```
각각의 서버의 도커에게 대신 지시해주는 오케스트레이션 도구
```

* Web Server / Web Application Server
```
Web Server : 정적 콘텐츠 처리 or 동적 콘텐츠 요청 WAS로 전달
Web Application Server : 동적 콘텐츠 생성 or 비즈니스 로직 수행
```

✅ Compile Time (컴파일 시간) vs Run Time (실행 시간)
| 구분    | Compile Time (컴파일 시간)   | Run Time (실행 시간)                        |
| ----- | ----------------------- | --------------------------------------- |
| 시점    | 코드 → 기계어로 **변환되는 시간**   | 프로그램이 **실제로 실행되는 시간**                   |
| 주체    | **컴파일러** (javac, gcc 등) | **운영체제 + CPU**                          |
| 관련 요소 | 문법 오류, 타입 검사, 선언 확인 등   | 로직 실행, 예외 발생, 메모리 동작 등                  |
| 오류 예시 | 문법 에러, 타입 불일치           | null pointer, divide by zero, 배열 인덱스 초과 |

* MVC 패턴
```
MVC 패턴은 Model + View + Controller를 합친 용어입니다. MVC 패턴의 구조, 동작, 특징, 장점, 단점을 이야기하겠습니다.

1) 구조
MVC는 Model + View + Controller를 말합니다.

Model : 어플리케이션에서 사용되는 데이터와 그 데이터를 처리하는 부분입니다.
View : 사용자에서 보여지는 UI 부분입니다.
Controller : 사용자의 입력(Action)을 받고 처리하는 부분입니다.

2) 동작
MVC 패턴의 동작 순서는 아래와 같습니다.

1. 사용자의 Action들은 Controller에 들어오게 됩니다.
2. Controller는 사용자의 Action를 확인하고, Model을 업데이트합니다.
3. Controller는 Model을 나타내줄 View를 선택합니다.
4. View는 Model을 이용하여 화면을 나타냅니다.

* 참고 - MVC에서 View가 업데이트 되는 방법

View가 Model을 이용하여 직접 업데이트 하는 방법
Model에서 View에게 Notify 하여 업데이트 하는 방법
View가 Polling으로  주기적으로 Model의 변경을 감지하여 업데이트 하는 방법.

3) 특징
Controller는 여러개의 View를 선택할 수 있는 1:n 구조입니다.
Controller는 View를 선택할 뿐 직접 업데이트 하지 않습니다. (View는 Controller를 알지 못합니다.)

4) 장점
MVC 패턴의 장점은 널리 사용되고 있는 패턴이라는 점에 걸맞게 가장 단순합니다. 단순하다 보니 보편적으로 많이 사용되는 디자인패턴입니다.

5) 단점
MVC 패턴의 단점은 View와 Model 사이의 의존성이 높다는 것입니다. View와 Model의 높은 의존성은 어플리케이션이 커질 수록 복잡하지고 유지보수가 어렵게 만들 수 있습니다.
출처: https://beomy.tistory.com/43 [beomy:티스토리]
```
![image](https://github.com/user-attachments/assets/5bcb0df5-cdea-4c96-988d-1c17a7583613)

* MVP 패턴
```
MVP 패턴은 Model + View + Presenter를 합친 용어입니다. Model과 View는 MVC 패턴과 동일하고, Controller 대신 Presenter가 존재합니다. MVP 패턴의 구조, 동작, 특징, 장점, 단점을 이야기하겠습니다.

1) 구조
MVP는 Model + View + Presenter를 말합니다.

Model : 어플리케이션에서 사용되는 데이터와 그 데이터를 처리하는 부분입니다.
View : 사용자에서 보여지는 UI 부분입니다.
Presenter : View에서 요청한 정보로 Model을 가공하여 View에 전달해 주는 부분입니다. View와 Model을 붙여주는 접착제..? 역할을 합니다.

2) 동작
MVP 패턴의 동작 순서는 아래와 같습니다.

1. 사용자의 Action들은 View를 통해 들어오게 됩니다.
2. View는 데이터를 Presenter에 요청합니다.
3. Presenter는 Model에게 데이터를 요청합니다.
4. Model은 Presenter에서 요청받은 데이터를 응답합니다.
5. Presenter는 View에게 데이터를 응답합니다.
6. View는 Presenter가 응답한 데이터를 이용하여 화면을 나타냅니다.

3) 특징
Presenter는 View와 Model의 인스턴스를 가지고 있어 둘을 연결하는 접착제 역할을 합니다.
Presenter와 View는 1:1 관계입니다.

4) 장점
MVP 패턴의 장점은 View와 Model의 의존성이 없다는 것입니다. MVP 패턴은 MVC 패턴의 단점이었던 View와 Model의 의존성을 해결하였습니다. (Presenter를 통해서만 데이터를 전달 받기 때문에..)

5) 단점
MVC 패턴의 단점인 View와 Model 사이의 의존성은 해결되었지만, View와 Presenter 사이의 의존성이 높은 가지게 되는 단점이 있습니다. 어플리케이션이 복잡해 질 수록 View와 Presenter 사이의 의존성이 강해지는 단점이 있습니다.
출처: https://beomy.tistory.com/43 [beomy:티스토리]
```
![image](https://github.com/user-attachments/assets/4b13cdc9-4a2f-4d5f-8cad-7746cddc4e82)

* MVVM 패턴
```
MVVM 패턴은 Model + View + View Model를 합친 용어입니다. Model과 View은 다른 패턴과 동일합니다. MVVM 패턴의 구조, 동작, 특징, 장점, 단점을 이야기하겠습니다.

1) 구조
MVVM는 Model + View + View Model를 말합니다.

Model : 어플리케이션에서 사용되는 데이터와 그 데이터를 처리하는 부분입니다.
View : 사용자에서 보여지는 UI 부분입니다.
View Model : View를 표현하기 위해 만든 View를 위한 Model입니다. View를 나타내 주기 위한 Model이자 View를 나타내기 위한 데이터 처리를 하는 부분입니다.

2) 동작
MVVM 패턴의 동작 순서는 아래와 같습니다.

1. 사용자의 Action들은 View를 통해 들어오게 됩니다.
2. View에 Action이 들어오면, Command 패턴으로 View Model에 Action을 전달합니다.
3. View Model은 Model에게 데이터를 요청합니다.
4. Model은 View Model에게 요청받은 데이터를 응답합니다.
5. View Model은 응답 받은 데이터를 가공하여 저장합니다.
6. View는 View Model과 Data Binding하여 화면을 나타냅니다.

3) 특징
MVVM 패턴은 Command 패턴과 Data Binding 두 가지 패턴을 사용하여 구현되었습니다. 
Command 패턴과 Data Binding을 이용하여 View와 View Model 사이의 의존성을 없앴습니다.
View Model과 View는 1:n 관계입니다.

4) 장점
MVVM 패턴은 View와 Model 사이의 의존성이 없습니다. 또한 Command 패턴과 Data Binding을 사용하여 View와 View Model 사이의 의존성 또한 없앤 디자인패턴입니다. 각각의 부분은 독립적이기 때문에 모듈화 하여 개발할 수 있습니다.

5) 단점
MVVM 패턴의 단점은 View Model의 설계가 쉽지 않다는 점입니다.
출처: https://beomy.tistory.com/43 [beomy:티스토리]
```
![image](https://github.com/user-attachments/assets/97f32e14-6a4c-4dec-b6ec-57703cddd723)


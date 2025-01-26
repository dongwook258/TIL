* 스프링 웹 개발 기초
```
정적 컨텐츠
MVC와 템플릿 엔진
API
```

* 정적 컨텐츠
```
resources/static/hello-static.html //static 폴더 하위에 생성
```html
<!DOCTYPE HTML>
<html>
<head>
 <title>static content</title>
 <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
</head>
<body>
정적 컨텐츠 입니다.
</body>
</html>
```
1. 관련 컨트롤러 찾기 우선
![image](https://github.com/dongwook258/TIL/assets/124165097/5229ab19-99e6-4f48-ae9b-3410e42abf49)

* MVC와 템플릿 엔진 (MVC: Model, View, Controller)

```
Controller

@Controller
public class HelloController {

    @GetMapping("hello-mvc")          //hello-mvc와 연결
    public String helloMvc(@RequestParam("name") String name, Model model) { //RequestParam 웹 브라우저에서 매개변수 받기
    model.addAttribute("name", name); //"name" = 키, name = 값
    return "hello-template";          //templates 하위 폴더의 hello-template 찾아서 실행
    }
}
```

```
View
resources/templates/hello-template.html //Controller가 찾을 위치

<html xmlns:th="http://www.thymeleaf.org"> //thymeleaf 받아야 함
<body>
<p th:text="'hello ' + ${name}">hello! empty</p> //${name}에 Controller의 (name = 값) 이 들어감
</body>
</html>

실행
http://localhost:8080/hello-mvc?name=spring!
```

![image](https://github.com/dongwook258/TIL/assets/124165097/a1588df9-af68-446f-a473-4b505d883cb4)

* API

```
@ResponseBody 문자 반환

@Controller
public class HelloController {
    @GetMapping("hello-string")
    @ResponseBody
    public String helloString(@RequestParam("name") String name) {
    return "hello " + name;
    }
}

@ResponseBody 를 사용하면 뷰 리졸버( viewResolver )를 사용하지 않음
대신에 HTTP의 BODY에 문자 내용을 직접 반환(HTML BODY TAG를 말하는 것이 아님)

실행
http://localhost:8080/hello-string?name=spring!
```

```
@ResponseBody 객체 반환

@Controller
public class HelloController {

    @GetMapping("hello-api")
    @ResponseBody
    public Hello helloApi(@RequestParam("name") String name) {
    Hello hello = new Hello();
    hello.setName(name);
    return hello;
    }

    static class Hello {

    private String name;

    public String getName() {
    return name;
    }

    public void setName(String name) {
    this.name = name;
    }

    }
}
@ResponseBody 를 사용하고, 객체를 반환하면 객체가 JSON으로 변환됨

실행
http://localhost:8080/hello-api?name=spring
```
![image](https://github.com/dongwook258/TIL/assets/124165097/72a9b8b1-b565-41af-9caf-f9a95787cb3b)
```
@ResponseBody 사용 원리

@ResponseBody 를 사용
HTTP의 BODY에 문자 내용을 직접 반환
viewResolver 대신에 HttpMessageConverter 가 동작
기본 문자처리: StringHttpMessageConverter
기본 객체처리: MappingJackson2HttpMessageConverter
byte 처리 등등 기타 여러 HttpMessageConverter가 기본으로 등록되어 있음
```

* 비지니스 요구사항 정리
![image](https://github.com/dongwook258/TIL/assets/124165097/6ef3d345-b349-44ab-93de-326abc90f287)
```
컨트롤러: 웹 MVC의 컨트롤러 역할
서비스: 핵심 비즈니스 로직 구현
리포지토리: 데이터베이스에 접근, 도메인 객체를 DB에 저장하고 관리
도메인: 비즈니스 도메인 객체, 예) 회원, 주문, 쿠폰 등등 주로 데이터베이스에 저장하고 관리됨
```

* 클래스 의존관계
![image](https://github.com/dongwook258/TIL/assets/124165097/00d7db7d-182d-40d2-86ae-8c22975d0493)

* 구현체 테스트
```
@AfterEach :
 한 번에 여러 테스트를 실행하면 메모리 DB에 직전 테스트의 결과가 남을 수 있다. 이렇게 되면 다음
이전 테스트 때문에 다음 테스트가 실패할 가능성이 있다. @AfterEach 를 사용하면 각 테스트가 종료
될 때 마다 이 기능을 실행한다.
@BeforeEach :
 각 테스트 실행 전에 호출된다. 테스트가 서로 영향이 없도록 항상 새로운 객체를 생성하고,
의존관계도 새로 맺어준다.
```

* 컴포넌트 스캔과 자동 의존관계 설정
```
컨트롤러에 의존관계 추가

생성자에 @Autowired 가 있으면 스프링이 연관된 객체를 스프링 컨테이너에서 찾아서 넣어준다. 이렇게
객체 의존관계를 외부에서 넣어주는 것을 DI (Dependency Injection), 의존성 주입이라 한다.
이전 테스트에서는 개발자가 직접 주입했고, 여기서는 @Autowired에 의해 스프링이 주입해준다.

@Component 애노테이션이 있으면 스프링 빈으로 자동 등록된다.

@Controller
@Service
@Repository
```
![image](https://github.com/dongwook258/TIL/assets/124165097/1f6e0f44-21c0-4ee3-ae56-fd5fb8ccdd20)

* 자바 코드로 직접 스프링 빈 등록하기
```
@Configuration
public class SpringConfig {
    @Bean
    public MemberService memberService() {
        return new MemberService(memberRepository());
    }
    @Bean
    public MemberRepository memberRepository() {
        return new MemoryMemberRepository();
    }
}

DI에는 필드 주입, setter 주입, 생성자 주입 3가지 방법이 있는데 생성자 주입 권장

실무에서는 주로 정형화된 컨트롤러, 서비스, 리포지토리 같은 코드는 컴포넌트 스캔을 사용한다.
그리고 정형화 되지 않거나, 상황에 따라 구현 클래스를 변경해야 하면 설정을 통해 스프링 빈으로 등록한다.

@Autowired 를 통한 DI는 helloController , memberService 등과 같이 스프링이 관리하는
객체에서만 동작한다. 스프링 빈으로 등록하지 않고 내가 직접 생성한 객체에서는 동작하지 않는다.
```

* @Configuration 어노테이션
```
스프링 IoC 컨테이너애게 Bean을 등록하는 클래스 임을 알린다
```

* @Bean 어노테이션
```
스프링 IoC 컨테이너가 관리하는 객체
의존성 주입 관리
```

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
```

![image](https://github.com/dongwook258/TIL/assets/124165097/a1588df9-af68-446f-a473-4b505d883cb4)

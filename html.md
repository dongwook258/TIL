* 강조 ```<strong> </strong>```
* 제목태그 ```<h1> </h1>```
* 하이퍼텍스트   
  새로운 창에서 열게 해주려면   
```<a href="https://developer.mozilla.org/ko/docs/Web/HTML/Element/a" target="_blank">a 태그</a>```   
즉, target="_blank" 를 적어주면 된다.
* 목록
```
<ol>
  <li>기술소개</li>
  <li>기본문법</li>
  <li>하이퍼텍스트와 속성</li>
  <li>리스트와 태그의 중첩</li>
</ol>
<ul>
  <li>최진혁</li>
  <li>최유빈</li>
  <li>한이람</li>
  <li>한이은</li>
</ul>
```
* 문서의 구조   
```
<!DOCTYPE html>                    // 선언 된 페이지의 html 버전이 무엇인지 표기
<html>
   <head>
     <title>HTML - 수업소개</title> // 웹페이지 제목 태그
     <meta charset="utf-8">        // 깨진 글자 처리
   </head>

   <body>
   </body>
</html>
```
* 단락
```
<p></p>
```
* 줄바꿈
```
<br>
```
* 이미지
```
<img src="001.jpg" width="100" height"200" alt="또니" title="또니 사진"> // alternative text(이미지 대체 텍스트)
```
* 테이블
```
<table border="2">                                                             // border(경계)
  <thead>                                                                      // table head
    <tr>                                                                       // table row
      <th>이름</th>    <th>성별</th>  <th>주소</th>               <th>회비</th> // table head(글씨 자동 굵어짐)
    </tr>
  </thead>
  <tbody>                                                                      // table body
    <tr>
      <td>최진혁</td>  <td>남자</td>  <td rowspan="2">청주</td>   <td>1000</td> // table data, rowspan(행합병)
    </tr>
    <tr>
      <td>최유빈</td>  <td>여자</td>    <td>500</td>
    </tr>
  </tbody>
  <tfoot>                                                                       // table foot
    <tr>
      <td colspan="3">합계</td>                                    <td>1500</td> // colspan(열합병)
    </tr>
  </tfoot>
```
---
* form
```
<form action="http://localhost/login.php">      // action(정보 저장 위치)
  <p>아이디 : <input type="text" name="id"></p> // type(입력 정보 유형), name(컨트롤 id)
  <p>비밀번호 : <input type="password" name="pwd"></p>
  <p>주소 : <input type="text" name="address"></p>
  <p>textarea : <textarea id="" cols="50" rows="2">default value</textarea></p> // textarea(여러 줄 입력)
  <input type="submit">
</form>
```
* 선택
```
<html>
    <head>
        <meta charset="utf-8">
    </head>
    <body>
        <form action="http://localhost/color.php">
            <h1>색상</h1>
            <select name="color">                   // name(입력 정보 유형)
                <option value="red">붉은색</option> // value(컨트롤 id)
                <option value="black">검은색</option>
                <option value="blue">파란색</option>
            </select>
            <h1>색상2 (다중선택)</h1>
            <select name="color2" multiple>         // multiple(다중 선택)
                <option value="red">붉은색</option>
                <option value="black">검은색</option>
                <option value="blue">파란색</option>
            </select>
            <input type="submit">
        </form>
    </body>
</html>
```
* 버튼
```
<html>
    <head>
        <meta charset="utf-8">
    </head>
    <body>
        <form action="http://localhost/form.php">
            <input type="text">
            <input type="submit" value="전송"> // value(이름)
            <input type="button" value="버튼" onclick="alert('hello world')">
            <input type="reset">
        </form>
    </body>
</html>
```
* hidden
```
<html>
    <head>
        <meta charset="utf-8">
    </head>
    <body>
        <form action="http://localhost/hidden.php">
            <input type="text" name="id">
            <input type="hidden" name="hide" value="egoing"> // ui에는 안 보이지만 숨겨진 데이터 전송
            <input type="submit">
        </form>
    </body>
</html>
```
* label(글자 클릭해도 커서가 위치함)
```
<html>
    <body>
        <form action=""></form>
            <p>
                <label for="id_txt">text</label> : // for과 id 같아야 함
                <input id="id_txt" type="text" name="id_txt" value="default value">
            </p>
            <p>
                <label for="password">password</label> : 
                <input id="password" type="password" name="pwd" value="default value">
            </p>
            <p>
                <label>textarea :                  // 전체를 label로 감싸도 됨
                <textarea cols="50" rows="2">default value</textarea>
                </label>
            </p>
            <p>
                <label>
                    <input type="checkbox" name="color" value="red">붉은색
                </label>
            </p>
            <p>
                <label for="color_blue">
                    <input id="color_blue"type="checkbox" name="color" value="blue">파란색
                </label>
            </p>
        </form>
    </body>
</html>
```
* method(get - url을 통해서 데이터 전송 / post - 데이터 숨겨서 전송)
```
<html>
    <head>
        <meta charset="utf-8">
    </head>
    <body>
        <form action="http://localhost/method.php" method="post"> // method(기본값은 get)
            <input type="text" name="id">
            <input type="password" name="pwd">
            <input type="submit">
        </form>
    </body>
</html>
```
* 파일 업로드
```
<html>
    <head>
        <meta charset="utf-8">
    </head>
    <body>
        <form action="http://localhost/upload.php" method="post" enctype="multipart/form-data">
                                               // 파일 전송하려면 method, enctype 필요
            <input type="file" name="profile"> // 파일의 name 필요
            <input type="submit">
        </form>
    </body>
</html>
```
* meta(태그가 감싸는 컨텐츠 설명)
```
<html>
    <head>
        <meta charset="utf-8">                                          // 기본 encoding = utf-8
        <meta name="description" content="생활코딩의 소개자료">          // 웹페이지 설명
        <meta name="keywords" content="코딩,coding,생활코딩,프로그래밍"> // 키워드
        <meta name="author" content="egoing">                           // 저자
        <meta http-equiv="refresh" content="10">                        // 10초마다 새로고침
    </head>
    <body>
        생활코딩은 일반인에게 프로그래밍을 알려주는 온라인/오프라인
        강의입니다.
    </body>
</html>
```
* semantic
```
<!DOCTYPE html>
<html>
<head>
  <title>HTML - 수업소개</title>
  <meta charset="utf-8">
</head>
<body>

<header>            // 헤더 명시
    <h1><a href="index.html">HTML</a></h1>
</header>

<nav>               // navigation 부분 명시
    <ol>
      <li><a href="1.html">기술소개</a></li>
      <li><a href="2.html">기본문법</a></li>
      <li><a href="3.html">하이퍼텍스트와 속성</a></li>
      <li><a href="4.html">리스트와 태그의 중첩</a></li>
    </ol>
</nav>

<section>            // 여러 부분 section으로 묶음
    <article>        // 본문 명시
        <h2>선행학습</h2>
        본 수업을 효과적으로 수행하기 위해서는 웹애플리케이션에 대한 전반적인 이해가 필요합니다. 이를 위해서 준비된 수업은 아래 링크를 통해서 접근하실 수 있습니다. 
    </article>
    <article>
        <h2>선행학습</h2>
        본 수업을 효과적으로 수행하기 위해서는 웹애플리케이션에 대한 전반적인 이해가 필요합니다. 이를 위해서 준비된 수업은 아래 링크를 통해서 접근하실 수 있습니다. 
    </article>
</section>

<footer>           // 최하단 명시
    <ul>
        <li><a href="privacy.html">개인보호정책</a></li>
        <li><a href="about.html">회사소개</a></li>
    </ul>
</footer>
</body>
</html>
* iframe(외부문서삽입)
```
<iframe src="iframe_source.html" frameborder="0" sandbox></iframe> // sandbox(javascript호출x / 데이터 전송 x)
```

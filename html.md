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
* form
```
<form action="http://localhost/login.php">      // action(정보 저장 위치)
  <p>아이디 : <input type="text" name="id"></p> // type(입력 정보 유형), name(컨트롤 id)
  <p>비밀번호 : <input type="password" name="pwd"></p>
  <p>주소 : <input type="text" name="address"></p>
  <input type="submit">
</form>
```

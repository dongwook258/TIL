```
style="color:red;text-decoration:underline" // style(html 속성), color:red(css 효과)
```
* 선택자와 선언, class, id
```
<head>
  <style>
    a {                                                         // tag selector(선택자)
        color: black;                                           // declaration(선언)
        text-decoration: none;
    }
    .saw {                                                      // class selector
        color: gray;
    }
    #active {                                                   // id selector
        color: red;
    }
    h1 {
          font-size: 45px;
          text-align: center;
    }
  </style>
</head>
<body>
  <h1><a href="index.html">WEB</a></h1>
    <ol>
      <li><a href="1.html" class="saw">HTML</a></li>            // calss
      <li><a href="2.html" class="saw" id="active">CSS</a></li> // class, id
      <li><a href="3.html">JavaScript</a></li>
    </ol>
  <h2>CSS</h2>
</body>
tag < class < id
```
* 조합 선택자
```
자식 : >        // h1 > span
자손 : 띄어쓰기 // h1 span
```
* 반응, 상태 선택자
```
반응 선택자 : hover(마우스 커서가 위에), active(활성화 된), visited
상태 선택자 : focus, enabled, disabled
```
* 특성 선택자
```
a[href=https://www.naver.com] {

                          }
```
* blcok level element(h1), inline element(a)
* 중복 제거 방법
```
h1, a{
      border: 5px solid red;
    }
```
* css 박스 모델
```
h1{
  padding: 20px;
  border: 5px solid red;
  margin: 20px;
  display: block;
  width: 100px;
}
```
* div(block), span(inline)
* display, float, position
```
display : block, inline-block, inline
float : left, right // 화면의 내용 무시하고 위치 조정
position : absolute, relative, fixed
```
* grid
```
<head>
  <meta charset="utf-8">
  <title></title>
    <style>
      #grid {
          border: 5px solid pink;
          display: grid;
          grid-template-columns: 150px 1fr; // 1fr(나머지)
            }
      div {
          border: 5px solid gray;
            }
    </style>
</head>
<body>
  <div id="grid">
    <div>NAVIGATION</div>
    <div>ARTICLE</div>
  </div>
</body>
```
* mediaquery(반응형)
```
@media(max-width:800px){ // 800px 보다 작으면 없애라
  div{
    display: none;
     }
}
```
* css 코드 재사용
```
<link rel="stylesheet" href="style.css"> // rel(ation 관계를 나타내 주는 필수 속성)
```

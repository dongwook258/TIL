* javascript 부분 명시
```
<script></script>
```
* 이벤트
```
<input type="button" value="hi" onclick="alert('hi')">
<input type="text" onchange="alert('changed')">
<input type="text" onkeydown="alert('key down')">
```
* 콘솔
```
개발자 도구의 콘솔기능을 활용하여 javascript 코드 실행 가능
```
* 제어할 태그 선택하기
```
<input type="button" value="night" onclick="
document.querySelector('body').style.backgroundColor = "black"
document.querySelector('body').style.color = "white"
```
* 태그 선택 후 순환 방법
```
function LinksSetColor(color) {
  var alist = document.querySelectorAll('a'); // 모든 태그 선택해서 배열에 저장
  for(var i = 0; i < alist.length; i++) {
    alist[i].style.color = color;
  }
}
```
* 객채 생성
```
var cowokers = {                                                  // 객체 생성
"programmer" : "egoing"
"designer" : "leezche"
};
document.write("programmer : " + cowokers.programmer + "<br>");
document.write("designer : " + cowokers.designer + "<br>");
cowokers.bookkeeper = "duru";                                     // 객체 추가
document.write("designer : " + cowokers.bookkeeper + "<br>");
cowokersp["data scientist"] = "taeho";                            // 띄어쓰기 있는 객체 추가
document.write("data scientis : " + cowokers["data scientist] + "<br>");
```
* 객체 데이터 순회 방법
```
for (var key in cowokers) {
  document.write(key + "<br>");           // 객체의 property 출력
}

for (var key in cowokers) {
  document.write(cowokers[key] + "<br>"); // 객체의 property에 해당하는 데이터 출력
}
```
* property(객체의 변수)와 method(객체의 함수)
```
cowokers.showAll = function() {
  for (var key in this) {
    if(key !== 'showAll')
    document.write(this[key] + "<br>")
  }
}
```
* 객체 활용하기
```
var Body = {
  setColor : function (color) {
    document.querySelector('body').style.color = color;
  },                                                     // 객체 property 구분

  setBackgroundColor : funciton (color) {
    document.querySelector('body').style.backgroundColor = color;
  }
}
```
* jQuery
```
<script src="https://code.jquery.com/jquery-latest.min.js"></script>
var Links = {
  setColor : function (color) {
  // var alist = document.querySelectorAll('a');
  // for(var i = 0; i < alist.length; i++) {
  //     alist[i].style.color = color;
  // }
  // }
  $('a').CSS('color', color); // 위 주석처리 된 코드와 동일
  }
}
```
* window.onloda , document.getElementById
```
window.onload = function(){ // 화면이 다 로딩 된 후 실행
            console.log("hello...4");
        };

document.getElementById("h01").innerText = "hello...1"; // 해당 id 찾아서 실행
```
* javaScript 검색 키워드
```
document 객체
- 페이지내의 태그 조작

DOM 객체
- document 객체로도 안되는 작업은 DOM문서를 확인

window 객체
- 웹페이지가 아닌 웹 브라우저 자체를 제어해야 하는 경우, 확인
- ex. 현재 열린 웹페이지의 주소가 필요한 경우,
새로운 브라우저 창을 열어야 할때.
브라우저 화면 크기 정보가 필요한 경우

Ajax 기술
- 웹페이지를 reload하지 않고, 정보를 변경하고 싶다면
- Morden web page 를 위한 필수 기술

Cookie 기술
- 웹페이지가 reload되어도 status를 유지해야 할 경우,
- 사용자를 위한 개인화된 서비스 제공

offline web application
- 인터넷이 끊겨도 동작하는 웹 페이지를 만들고 싶다

WebRTC
- 화상통신 웹 애플리케이션을 만들어야 한다면

Speech API
- 사용자의 음성을 처리하고 싶다면

webGL
- 3차원 그래픽으로 게임같은 것을 만들고 싶다면

webVR
- 가상 현실
```

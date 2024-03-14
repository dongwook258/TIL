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
  document.write(key + "<br>");           // 객체의 key값 출력
}

for (var key in cowokers) {
  document.write(cowokers[key] + "<br>"); // 객체의 key값에 해당하는 데이터 출력
}
```

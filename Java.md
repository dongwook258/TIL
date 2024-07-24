* Hello Java
```
public class HelloJava {
  public static void main(String[] args) { //psvm
    System.out.println("Hello Java");      //sout
  }
}
```
* 사용자 입력 받기
```
package scanner;

import java.util.Scanner;

public class Scanner1 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("문자열을 입력하세요:");
        String str = scanner.nextLine();
        System.out.println("입력한 문자열: " + str);

        System.out.print("정수를 입력하세요:");
        int intValue = scanner.nextInt();
        System.out.println("입력한 정수: " + intValue);

        System.out.print("실수를 입력하세요:");
        double doubleValue = scanner.nextDouble();
        System.out.println("입력한 실수: " + doubleValue);
    }
}
```
* BufferedReader / BufferedWriter
```
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.InputStreamReader;
import java.io.OutputStreamWriter;
```
```
BufferedReader br = new BufferedReader(new InputStreamReader(System.in)); //선언
String s = br.readLine(); //String
int i = Integer.parseInt(br.readLine()); //Int

 throw 이용 시
(1) 클래스를 import해주어야 한다. 
import java.io.IOException; 
(2) main 클래스 옆에 throws IOException를 작성한다. 
public static void main(String[] args) throws IOException {}
```
```
BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));   //할당된 버퍼에 값 넣어주기
String s = "abcdefg";   //출력할 문자열
bw.write(s+"\n");   //버퍼에 있는 값 전부 출력
bw.flush();   //남아있는 데이터를 모두 출력시킴
bw.close();   //스트림을 닫음
```
* StringTokenizer
```
import java.util.StringTokenizer;

StringTokenizer st = new StringTokenizer(s); //StringTokenizer인자값에 입력 문자열 넣음
int a = Integer.parseInt(st.nextToken()); //첫번째 호출
int b = Integer.parseInt(st.nextToken()); //두번째 호출

String array[] = s.split(" "); //공백마다 데이터 끊어서 배열에 넣음
```
* StringBuilder
```
StringBuilder sb = new StringBuilder();

sb.append(a+b).append("\n");
```
* 배열
```
int[] a;
a = new int[] {90, 80, 70, 60, 50};

int[] a = new int[5]; //[]안에 배열의 크기 지정 필수

int[] a = {90, 80, 70, 60, 50};
```
* 향상 된 for 문
```
int[] numbers = {90, 80, 70, 60, 50};

for (int number : numbers)
```
* java.lang 패키지의 대표적인 클래스들
```
Object : 모든 자바 객체의 부모 클래스
String : 문자열
Integer , Long , Double : 래퍼 타입, 기본형 데이터 타입을 객체로 만든 것
Class : 클래스 메타 정보
System : 시스템과 관련된 기본 기능들을 제공
```


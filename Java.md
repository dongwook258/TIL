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

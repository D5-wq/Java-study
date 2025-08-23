8. 훈련
- Scanner 학습

지금까지 배운 기본기를 연습하는 시간이다. 

scanner라는 class를 이용한다. (package scanner)

동적 메모리 할당

Scanner scanner = new Scanner(System.in);

scanner.nextLine()는 Enter를 입력할 때까지 문자를 그대로 가져오는 것이다. nextInt, nextdouble도 마찬가지이다. 

print/println - 줄 바꿈 유무 차이가 있다.

- Scanner 기본 예제

두 수의 합을 계산

int num1= scanner.nextInt();

int num2= scanner.nextInt();

sum = num1 + num2

System.out.println(sum); 출력 

- Scanner 반복 예제

실제 프로그램들은 한 번의 결과만 출력하고 종료되지 않는다.

while(true)를 이용한다. 내용을 작성하고

if(str.equals(”exit”)) {break;} 를 통해 while문을 빠져나간다.

또 다른 예제: if (num1 == 0 && num2 ==0) break;

입력한 정수들의 합 출력: sum += number

- 문제와 풀이1

-이름과 나이를 받고 출력하기

```java
package scanner.ex;

import java.util.Scanner;

public class ScannerEx1{

public static void main(String[] args){

Scanner scanner = new Scanner(System.in);

System.out.print(”당신의 이름을 입력하세요:”);

String name = scanner.nextLine();

age - nextInt();

System.out.println(”당신의 이름은 “ + name + “이고, 나이는 “ + age + “살입니다.” 

}

}
```

-홀수 짝수

if (number % 2 ==0) 짝수

else 홀수

-음식 이름 가격 수량, 총 가격 계산하고 출력하기

String foodName = scanner.nextLine();

int foodPrice = input.nextInt(); 

food Quantity 동일

totalPrice 출력

-구구단 n단 출력

int n = input.nextInt();

for( int i=1 ; i≤9; i++){ System.out.println(n + “ x “ + i + “ = ” + n*1);

- 문제와 풀이2

-swap 

int a = 10; int b=20;

temp를 이용

temp=a;

a=b;

b= temp;

-사이 숫자

num1 부터 num2까지의 숫자 출력 (오름차순으로)

if (num1> num2) 숫자 교환 swap

for (i = num1; i≤num2; i++) System.out.print(i)

if (i≠num2) System.out.print(”,”);

- 문제와 풀이3

-이름과 나이 반복

while(true) if(name.equals(”종료”) break;

input.NextInt에서 10을 쓰고 Enter를 누르면 입력 자체는 10/n이 되기 때문에 뒤에 input.NextLine을 이용해 /n을 읽고 버린다.

```java
package scanner.ex;
import java.util.Scanner;

public class Scanner{

public static void main(String[] args)
{ Scanner scanner = new scanner(System.in)
```

- 문제와 풀이4
- 퀴즈
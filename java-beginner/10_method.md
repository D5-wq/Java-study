10. 메서드
- 메서드 시작

int a=1, b=2일때 a+b 계산 가능

이러한 덧셈을 여러번 하고 싶을 때 메서드, 함수 이용

add(a,b) = a+b

avg(a,b) = (a+b)/2

자바에서는 함수를 메서드라고 한다.

- 메서드 사용

```java
package method;

public class Main {
    public static void main(String[] args) {

        int a = 1;
        int b = 2;
        System.out.println(a +  "+" + b + "연산 수행");

        int sum1 = a + b;
        System.out.println("결과1 출력: " + sum1);

        System.out.println("======================");

        int x = 10;
        int y = 20;
        System.out.println(x + "+" + y + "연산 수행");

        int sum2 = x + y;
        System.out.println("결과2 출력: " + sum1);
    }
}
```

이런 식으로 비슷한 덧셈을 여러 번 해야 할 때 매번 작성 대신 메서드 사용

```java
public static int add(int a, int b){
		System.out.println(a + "+" + b + "연산 수행");
		int sum = a + b;
		return sum
	}
```

int sum = add (5,10) 이런 식으로 활용하면 된다.

메서드 선언

public - 다른 클래스에서 호출 가능

static - 정적, 객체 생성 X

int - 반환 타입

add- 메서드 이름

(int a, int b) - parameter

메서드 본문 - 상황에 맞게 작성

메서드 호출 - 반환한 결과 값으로 치환됨

- 메서드 정의

제어자, 반환 타입, 이름, 매개 변수를 작성한 뒤 아래 본문 작성

매개변수가 없거나 반환 타입이 없는 경우(void 타입)

```java
public static void printHeader(){
		System.out.println("= 프로그램을 시작합니다 = "
		return;
}

public static void printFooter(){
		System.out.println("= 프로그램을 종료합니다 = "
}
```

printHeader() 로 실행

반환 타입을 받으면 컴파일 오류가 발생함

return은 메서드에서 항상 들어가야함. 없으면 java가 알아서 넣어준다고 생각.

- 반환 타입

```java
public static boolean odd(int i){
		if(i % 2 == 1){
				return true;
		} else {
				return false;
		} 
}
```

else의 경우를 생략하게 되면 return이 존재하지 않는 경우가 발생하므로 조건문 사용 시 모든 경우에 return을 포함하도록 해야 함.

실행 중 return을 만나면 바로 로직을 빠져나감 

- 메서드 호출과 값 전달 1

*** 자바는 항상 변수의 값을 복사해서 대입한다.

```java
int num1 = 5;
int num2 = num1;
num2 = 10;
```

num1 = 5 , num2 = 10임 num2에 num1 자체를 넣는 것이 아닌 값만 복사해서 넣는 것. 

 num1과 num2는 아무 관계없음

```java
public static void main(String[] args) {
		int num1 =5;
		System.out.println(num1);
		changeNumber(num1);
		System.out.println(num1);
	}

public static void changeNumber(int num2){
		System.out.println(num2);
		num2 = num2*2;
		System.out.println(num2);		
}
```

5 5 10 5라는 결과값이 나온다.

처음 num1 출력 =5

changeNumber로 넘어간 5

두배가 곱해진 10

그렇지만 그 값은 changeNumber 내에서만 유효한 숫자이므로 다시 num1 5가 출력됨.

- 메서드 호출과 값 전달 2

사용하는 변수와 매개변수의 이름을 같게 number라고 해보자. 물론 결과값은 같다.

main 과 changeNumber 메모리 공간에 각각 생기는 완전히 다른 변수라고 생각해야 한다.

그럼 의도에 맞게 두배를 리턴받아서 사용하고 싶으면 어떻게 해야 될까?

```java
public static void main(String[] args) {
		int num1 =5;
		System.out.println(num1);
		changeNumber(num1);
		System.out.println(num1);
	}

public static void changeNumber(int num2){
		num2 = num2*2;
		return num2;
}
```

값을 돌려주는 return을 작성하면 된다.

출력되는 값은 5 10이 될것이다.

- 메서드와 형변환

명시적 형변환

double number = 1.5을 매개변수가 int n인 메서드 printNumber에 넣으면 컴파일 오류 발생(더 좁은 범위에 대입 X)

printNumber((int) number); 의 형태로 쓰면 됨

자동 형변환

int < long < double

int number = 100을 매개변수가 double n인 메서드 printNumber에 넣으면 아무 문제 없음. (자동으로 형변환 적용됨)

- 메서드 오버로딩

숫자를 2개를 더할수도 있지만 3개 이상을 더할수도 있다.

add(int a, int b)

add(int a, int b, int c)

add(double a, double b)

같은 이름의 메서드를 여러 개 정의할 수 있다.

int add, double add 의 반환 타입이 다른 경우는 인정하지 않는다. (method signature = 메서드 이름 + 매개변수 타입 / 메서드 시그니처가 같으면 오류 발생)

- 문제와 풀이
1. sum = a+b+c , average = sum / 3.0을 메서드로 작성하기

반환 타입은 double

```java
public static double average(int a, int b, int c){
		int sum = a + b + c;
		return sum / 3.0;
}
```

1. 특정 숫자만큼 같은 메세지 반복

```java
public static void printMessage(String message, int times){
		for (int i=0 ; i < times ; i++){
				System.out.println(message);
		}
}
```

1. 은행 입출금 처리

```java
public static int deposit(int balance, int amount)[
		balance += amount;
		System.out.println(amount+"원을 입금하였습니다. 현재 잔액 : " + balance + "원");
		return balance;
}
```

- 정리

- 다음으로

- Q&A

자바는 왜 다른 언어와  다르게 Scanner를 사용해야만 입력을 받을 수 있을까? C프로그래밍에서처럼 scanf나 C++의 cin>> 같은 구문이 없을까? 왜 input과 output의 구조가 동등하지 않을까?

— Java에서 Scanner를 사용해야만 입력을 받을 수 있는 이유는 객체지향프로그래밍에 담겨 있다.  C에서 사용한 scanf()의 경우 전역 함수이지만 Java는 C와 달리 모든 기능을 클래스와 그 안의 메서드로 감싸는 구조를 가지고 있다. System.in이라는 입력 스트림 객체를 사용한다.

Java는 축약 코드보다 명시적인 Scanner scanner = new Scanner([System.in](http://system.in/));의 코드를 더 선호하는 언어이다.

또한 출력은 PrintStream, 입력은 InputStream의 다른 객체를 사용하는데 출력은 대부분 텍스트이고 대상이 정해져있기 때문에 초창기부터 단순하게 고수준으로 시작할 수 있었지만, 입력은 출처가 다양하고 복잡해서 그렇지 못했다.

C와 C++는 콘솔 기반 프로그램이 기본이라 입출력을 동등하게 단순화(대칭적)했고 , Java는 플랫폼 독립성과 객체지향에 더 초점을 두고 입출력을 다르게 설계함.(비대칭적)
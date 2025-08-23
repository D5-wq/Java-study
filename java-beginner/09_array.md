9. 배열
- 배열 시작

```java
package array;

public class Array1 {

	public static void main(String[] args){
			int student1 = 90;
			int student2 = 80;
			int student3 = 70;
			int student4 = 60;
			int student5 = 50;
			
			System.out.println("학생1 점수: " +student1);
			
				}
			}
```

학생 수를 추가함에 따라 코딩 양이 매우 증가함.

반복문으로 해결하고 싶을 수 있지만 불가함. 변수 이름이 다르다. → 배열 이용

- 배열의 선언과 생성

인덱스 (0에서 n-1번까지 총 n개)

students[0] = 90;

students[1] = 80;

…

배열 값 읽기, 대입하기 가능

-기본형 vs 참조형

기본형 : int, long, double, boolean처럼 변수에 사용할 값을 직접 넣을 수 있음.

참조형 : int [] students와 같이 데이터에 접근하기 위한 참조(주소)를 저장하는 데이터 타입. 객체, 클래스, 배열

참조형은 동적으로 크기를 바꿀 수 있기 때문에 배열은 참조형을 사용한다.

- 배열 리펙토링

리펙토링이란 기능 자체는 동일하지만 가독성과 유지보수 측면에서 코드의 내부 구조를 개선하는 것을 뜻한다.

System.out.println(”학생1 점수: “ + students[0]); 1,2,3,4,5 반복보다

```java
for (int i=0; i<5; i++){
		System.out.println("학생" + (i + 1) + "점수: " + students[i]);
```

가 더 좋은 코드이다.

-초기화

```java
public class Array3 {

		public static void main(String[] args){
			int[] students = new int[]{90,80,70,60,50};
			
			
			for (int i=0 ; i < students.length; i++){
					System.out.println("학생" + (i+1) + "점수 + students[i]);
					}
			}
}
			
			
```

- 2차원 배열 - 시작

행렬처럼 int[][] arr = new int[2][3]와 같이 선언.

행: 가로 줄 개수

열: 세로 줄 개수

1 2 3

4 5 6

arr[0][0] = 1 , arr[0][1] = 2 ,  arr[0][2] =3 , arr[1][0] = 4 , arr[1][1] = 5 , arr[1][2] = 6 이다.

- 2차원 배열 - 리팩토링1

위처럼 일일히 다 작성할수도 있지만, for문을 통해 차례로 값을 입력할 수 있다.

```java
for(int i=0; i<2; i++){
	for(int j=0; j<3; j++){
		System.out.print(arr[i][j]+" ");
		}
		System.out.println();
	}
```

- 2차원 배열 - 리팩토링2

```java
int[][] arr = {
	{1,2,3},
	{4,5,6}
	};
	
	for (int i=0; i<arr.length; i++){
		for(int j=0 j<arr[i].length; j++){
			System.out.print(arr[i][j] + " ");
			}
		System.out.println();
	}
```

- 향상된 for문

enhanced for

int[] numbers = {1, 2, 3, 4, 5};

int num

for (int number : numbers){

System.out.println(number);

}

- 문제와 풀이 1

점수 90,80,70,60,50을 배열에 넣고 

int [] students = {90,80,70,60,50};

int total = 0;

for ( int i=0; i<students.length; i++){

total += students[i];

}

double average = total / 5;

— import java .util.scanner;

Scanner scanner = new Scanner(System.in);

- 문제와 풀이 2,3
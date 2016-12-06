#Introduction to C programming

</br>



## 프로그램 작성하기 전에

### 프로그램 작성법
- // 또는 /* */ 로 커맨팅한다
- 각 문장의 끝마다 ; 를 반드시 붙여주어야 한다

### C와 함수

- C는 함수들로 구성되어 있고, 함수로 시작해서 함수로 끝난다. 
- 정해진 순서에 의해 진행되는 함수의 호출이 프로그램의 흐름이다.
- 가장 먼저 호출되는 함수는 main이며, 모든 c 프로그램에 있다.

```
#include <stdio.h> 
//printf와 같은 표준함수 호출을 위해 헤더파일 선언을 한다. 맨 앞에 와야함.
int main(void) // 출력형태 함수이름(입력형태) {함수의 몸체}
{
	printf("Hello world! \n"); 
	return 0; //함수 내 존재하는 모든 문장의 끝에는 세미콜론을 붙인다. 
}
```


## 변수, 상수 그리고 연산자


- 변수 : 값을 저장할 수 있는 메모리 공간에 붙은 이름. 이것을 통해서 메모리 공간에 접근 가능
- 변수 사용으로 연산한 뒤 값을 저장하고 저장된 값을 참조할 수 있음
- 연산자 : 특정 연산을 요구할 때 사용하는 약속된 기호

### 변수의 선언
```
int nSamp; //nSamp이라는 이름의, int 타입의 변수를 선언
```
- 변수를 선언한 다음에는 변수에 값을 저장하고, 참조하고 저장된 값을 변경할 수 있다
- 반드시 프로그램의 맨 앞머리에 변수 선언을 해두어야 한다

### 변수에 값 저장
```
int main(void)
{
	int nSamp; //nSamp이라는 이름의, int 타입의 변수를 선언
	nSamp = 20; // 변수에 20 저장. 처음 값을 저장하는 것을 초기화라고 한다.
	printf("%d", nSamp); // 변수 nSamp의 값 참조해서 모니터 출력
	return 0; // 프로그램이 잘 작동되었다는 표시로 0을 return
}
```
- 변수를 선언만 하고 초기화하지 않으면 쓰레기값이 저장되므로, 0으로 초기화해주는 것이 좋다. 
- 중괄호 내 변수 선언시, 선언문은 앞부분에 위치해야 한다.

### 변수의 자료형
- 크게 정수형 변수, 실수형 변수로 나눠진다
- 정수형 변수는 크기에 따라 char, short, int, long으로 나눠지고, 실수형 변수도 크기에 따라  float, double로 나눠진다.

### 데이터 표현 방식의 이해

- 비트 : 컴퓨터가 표현하는 데이터의 최소단위로서 2진수 값 하나를 저장할 수 있는 메모리의 크기

- 바이트 : 8개 비트가 모여서 1바이트가 됨

- 1바이트 기준으로 정수의 표현방식을 설명하자면 8개의 비트 중 가장 앞의 비트 한 개는 부호를 표시하고 나머지 비트들은 정수의 크기를 나타낸다. 

- 컴퓨터는 실수를 정확하게 표현하지 못한다. 다만 근사치만을 나타낼 뿐

- char 은 문자를 표현하기 위해 쓰이긴 하지만 정수의 형태로 표현되고 실제로 저장되는 것도 정수이다. 각 alphabet에 어떤 정수가 매칭되는지는 아스키코드를 보면 알 수 있다

### 상수

- 상수 : 변경이 불가능한 데이터
- 이름이 없는 상수를 리터럴(혹은 리터럴 상수)이라 하고, 이름 있는 상수를 const상수라 한다

```
int main(void)
{
	int num = 30 + 40 //30 과 40은 리터럴 상수
	// 정수 30과 40이 메모리 공간에 상수의 형태로 저장되고
	// 두 상수를 기반으로 덧셈
	// 덧셈의 결과로 얻어진 70이 변수 num에 저장
	return 0;
}

```

### 자료형 변환

- 자동으로 되는 경우도 있고 수동으로 되는 경우도 있다
- ex) 대입연산 전달과정에서 발생하는 자동 형 변환. 예를 들면 double num1 = 24;
24라는 int를 double로 자동으로 바꿔줌
- ex) int num = 2 라고 초기화 시킨다음 double num하는 것은 강제 형변환

### 연산자
- 대입 연산자 = 와 산술 연산자 +, -, *, /, %
- 복합 대입 연산자: *=, /=, %=, +=, -=, <<=, >>=, &=, ^=, |= 두 개의 피연산자에 대해서, 앞의 연산을 실행한다음 왼쪽 변수에 대입
- +, - 는 부호의 의미를 가지기도 한다. 

```
int main(void)
{
	int num1=2, num2=4, num3=6;
	num1 += 3; //num1 = num1 + 3;
	num2 *= 4; //num2 = num2 + 4;
	num3 %= 5; //num3 = num3 + 5;
	num1 = -num1 ; 이 때 -는 부호의 의미
	num1 -= num1
	printf("Result: %d, %d, %d\n", num1, num2, num3)
	return0;
}
```

- 증가, 감소 연산자: 변수에 저장된 값을 1 증가 혹은 감소시키는 경우의 연산자
- ++num, --num, num++, num--

```
int main(void)
{
	int num1 = 12;
	int num2 = 12;
	printf("num1++: %d \n", num1++); //후위 증가
	// 후위증가란, 속한 문장을 먼저 실행한 후 변수 값을 1증가시키는 것이다
	// 따라서 여기에선 printf가 실행된 후 num1이 13이 되므로, 프린트 되는 값은 12
	printf("++num2: %d \n", ++num2); //전위 증가
	// 전위증가란,  변수 값을 1증가시킨 후 속한 문장을 실행하는 거이다
	// 따라서 여기에서 프린트되는 값은 13

	int num2 = (num1--)+2; //이런 경우는 어떡하지?
	//원래 소괄호로 묶은 문장을 먼저 실행해야하지만, 후위증가및 후위감소시에는
	//소괄호 영향 안받아 
	return 0;
}
```
- 비트 연산자 : &, |, ^, ~, <<, >> 비트 단위의 연산을 하는 연산자들이다.


## 입출력 함수

- 컴퓨터의 연산은 입력과 출력을 통해 이루어진다.

### 문자 입출력 함수

### 문자열 입출력 함수

- getchar : 키보드 입출력 버퍼(메모리의 한 종류)에 저장된 문자/문자열 중 한 글자 읽어옴. 버퍼가 비어있으면 키보드 입력을 기다리고 있음. 버퍼가 채워져있으면 그 문자를 반환
- getch, getche : getch는 getchar 와 비슷하지만 버퍼를 거치지 않고 입력받은 문자 한 글자를 바로 받는다. getche는 getch에 출력기능도 있음

```
int getchar(void);
```

- putchar : 문자를 모니터에 출력

```
int putchar(int c);
```

- pritnf : 출력. scanf : 입력
- scanf 함수는 공백을 기준으로 데이터의 수를 구분한다. 따라서 공백을 포함하는 문자열을 한번의 scanf 함수호 출을 통해서 읽어 들이지는 못힌다.
- scanf가 입력받는 변수 앞에는 항상 &을 쓴다. 문제열 제외

```
int main (void
{
	int nSamp1, nSamp2, nSamp3;
	printf("세 개의 정수 입력: ");
	scanf("%d %o %x , &nSamp1, &nSamp2, &nSamp3);
	
	printf("%d %d %d \n", nSamp1, nSamp2, nSamp3);

}

```


## 반복문
 
### While : 반복을 명령하는 문장
```
while(num<3) //반복의 조건은 num<3
{
	printf("hello world/n");
	num++;
}
// while문 소괄호 안에는 반복의 조건. 이 조건이 참이되는 동안에는 중괄호 안 코드가 계속 실행된다
```
- do ~ while 문. 반복조건을 뒤에서 검사하기 때문에, 반복영역을 적어도 한 번은 실행한다

```
do //일단 밑의 실행문 적어도 한 번은 실행
{
	printf("hello world/n");
	num++;
}while(num<3)
```

### For문 
- 반복을 위한 변수 선언과 반복조건을 거짓으로 만들기 위한 값의 증가 및 감소
- 반복의 횟수가 정해진 경우 while보다 유리
- 초기식(반복을 위한 변수의 선언 및 초기화), 조건식(반복의 조건을 검사), 증감식(반복의 조건을 '거짓'으로 만드는 증가 및 감소연산) 으로 이루어짐

```

int main(void)
{
	for (int num =0; num < 3; num++)
		printf("Hi~"); // 반복의 대상이 한 줄이라 중괄호 생략
	return 0;

}


for (초기식; 조건식; 증감식)
{
	//반복의 대상이 되는 문장들
}
``` 

## 조건문

```
if(조건1)
{
//조건 1 만족 시 실행
}
else if(조건2)
{
//조건 2 만족 시 실행. else if 얼마든지 추가 삽입가능
}
else
{
//모두 불만족 시 실행
}
```

- 조건 연산자: if~ else 문을 일부 대체 할 수 있음

```
(num1>num2) ? (num1) : (num2) ;

(조건) ? data1 : data2
조건이 참이면 data1이 반환되고 거짓이면 data2가 반환된다

int num3 = (num1>num2) ? (num1) : (num2);
```

### 반복문 생략과 탈출

- break : break문을 가장 가까이서 감싸고 있는 반복문 하나를 빠져나온다
- continue: 실행중인 위치에 상관없이 반복문의 조건검사 위치로 이동한다. 그리고 검사결과 참이면 반복영역을 다시실행한다

```
int main(void)
{
	while(1)
	{
		if(x>20)
		break; //x>20이면 while문 탈출
	}
}

int main(void)
{
	while(1)
	{
		if(x/2==1)
		continue; // x/2==1 조건검사로 이동
	}
	
	return 0;
}
```
- break, continue 모두 if와 자주 같이 쓰이지만 if 문을 탈출하거나, if 문의 조건절로 돌아가는 것이 아니라는 것 명심

- switch문도 있는데 뭐 다 똑같아... 

```
switch(n)
{
case 1:
	printf("AAA");
	break;
case 2:
	printf("BBB");
	break;
case 3:
	printf("CCC");
	break;
default:
	printf("Hi")
}
//주의해야 될 건 case문에 break쓰는 거랑
//if 문에선 else에 해당하는 게 여기선 default라는 것 정도
```

## 함수

- 함수의 크기는 작을수록 좋고, 하나의 함수는 하나의 일을 담당하게 해야한다
-  유형 1: 전달인자 있고, 반환 값 있다! 전달인자(○), 반환 값(○) 유형 2: 전달인자 있고, 반환 값 없다! 전달인자(○), 반환 값(x) 유형 3: 전달인자 없고, 반환 값 있다! 전달인자(x), 반환 값(○) 유형 4: 전달인자 없고, 반환 값 없다! 전달인자(x), 반환 값(x)


```
int Add(int num1, int num2) //유형1
{
	int result = num1 + num2;
	
	return result;
}

void ShowAddResult(int num) //유형2
{
	printf("덧셈결과출력 : %d \n", num);
}

int ReadNum(void) // 유형3
{
	int num;
	scanf("%d" , &num); //뒤에서 배울테지만, &연산자는 주소값을 반환한다
	return num;
}

void HowToThisProg(void) //유형4
{
	printf("이제 가보자! \n");
}

// 이제 위의 네 개를 사용해보자

int main(void)
{
	int result, num1, num2;
	HowToThisProg();
	num1 = ReadNum();
	num2 = ReadNum();

}

```

- 값을 반환하지 않는 return

```
void NoReturnType(int num) 
{
	if(num<0)
	return;
	
}
// return 문은 '값의 반환' 과 '함수의 탈출'이라는 두 가지 기능이 담겨있다.
// return 문이 꼭 끝에 와야 할 필욘 없고 중간에도 올 수 있다
// 여기서는 값을 반환하지 않고 함수만 탈출
```

- 함수의 선언 : 컴파일이 위에서 아래로 진행되어, 미리 선언되지 않은 함수는 쓰일 수가 없다. 그래서 함수를 일단 선언하고 그 다음 정의해줌

```
int Increment(int n); //함수의 선언

int main(void)
{
	int num =2;
	num = Increment(num);
	return 0;
}

int Increment(int n) //함수의 정의
{
	n++;
	return n;
}
```

## 변수의 존재기간과 접근 범위

- 지역변수 : 함수 내에 선언되는 변수를 가리켜 지역변수라 핚다.지역변수는 선언된 이후로부터 함수 내에서맊 접근이 가능하다.한 지역(함수) 내에 동일핚 이름의 변수 선언 불 가능하다.다른 지역에 동일한 이름의 변수 선언 가능하다.해당 지역을 빠져나가면 지역변수는 소멸된다. 그리고 호출될 때마다 새롭게 할당된다.

```
int SimpleFuncOne(void)
{
	int num = 10;
	num++;
	printf("SimpleFuncOne: %d \n" , num);
	return 0;
}

int SimpleFuncTwo(void)
{
	int num1 = 20;
	int num2 = 30;
	num1++ , num2--;
	printf("num1 & num2 : %d %d \n" , num1, num2);
	return 0;
}

int main(void)
{
	int num =17;
	SimpleFuncOne();
	SimpleFuncTwo();
	printf("main num: %d \n", num);
	return 0;
}
```

- for 문의 중괄호 안에 선언된 변수도 일종의 지역변수이다.
- 지역변수는 외부에 선언된 동일한 이름의 변수를 가린다
- 매개변수(parameter)는 일종의 지역변수이다

- 전역변수 : 전역변수는 함수 외부에 선언된다.프로그램의 시작과 동시에 메모리 공갂에 할당되어 종료시까지 존재한다.별도의 값으로 초기화하지 않으면 0으로 초기화된다.프로그램 전체 영역 어디서든 접근이 가능하다.

- 지역변수의 이름이 전역변수의 이름을 가린다
- 전역변수는 많이 쓰면 좋지 않다...

- static변수 : 선언된 함수 내에서만 접근이 가능하다. (지역변수 특성)딱 1회 초기화되고 프로그램 종료 시까지 메모리 공간에 존재핚다. (전역변수 특성)

- register변수 : “이 변수는 내가 빈번히 사용하거든, 그래서 접근이 가장 빠른 레지스터에 저장하는 것이 성능향상에 도움이 될 거야” (레지스터는 CPU 내부에 존재하는, 때문에 접근이 가장 빠른 메모리 장치이다. )

- static 변수, register 변수 모두 선언할 때 그냥 앞에다 static, register 붙여주면 된다. static int num2 = 10; 이렇게


## 재귀함수에 대한 이해

- 자료구조에서 빈번하게 나온다!! 중요중요


## 배열

- 배열 : 다수의 변수를 선언하기 위한 자료구조 

```
//배열 선언에 필요한 3가지
int oneDimArr[4];
변수타입 배열이름[배열크기]

//배열에 접근
arr[0] = 10; //배열의 첫번째 요소에 10을 저장해라

//선언과 동시에 초기화
int arr1[5] = {1,2,3,4,5}
int arr1[5] = {1,2} //초기화 값이 부족한 경우 나머지는 0으로 채워짐
int arr1[] = {1,2} //길이정보 없으면 컴파일러가 메꿔준다

//배열의 크기

sizeof(arr1) //배열의 크기를 바이트 크기 정보로 반환

```
int arr1[5] = {1,2,3,4,5};
printf("배열 arr1의 크기: %d \n", sizeof(arr1));
ar1Len = sizeof(arr1) / sizeof(int); //  이래야지 배열의 길이를 계산가능
```

- 문자형 배열

```
char str[14]= "Good Morning!";
//배열로 저장될 때, 문자열의 끝에는 널문자라고 불리는 \0가 삽입된다. 문자열의 끝을 의미한다
//널문자가 공백문자는 아니다


```
- scanf 함수를 통해 입력받을 때 &연산자를 쓰지 않아도 된다
```
scanf("%s", str); 
``` 


## 포인터란 무엇인가?

- 포인터 : 주소 값을 저장하는 목적으로 선언되는 것이 포인터 변수이다. 포인터 변수의 크기는 시스템 주소 값 크기에 따라 다름

```


/* “정수 7이 저장된 int형 변수 num을 선언하고 
이 변수의 주소 값 저장을 위한 포인터 변수 pnum을 선언하자. 
그리고 나서 pnum에 변수 num의 주소 값을 저장하자.” */

int main(void) 
{
	int num = 7;
	int * pnum; // 포인터 변수 선언
	pnum = &num; //num의 주소값을 pnum에 저장 & 연산자의 피연산자는 변수여야 한다
	//&연산자의 반환값은 항상 포인터변수에 저장해야 한다.
}

// 이 상태를 다음과 같이 표현한다
// 포인터 변수 pnum이 num을 가리킨다

// 꼭 포인터변수가 정수형으로 선언될 필욘 없음
int * pnum1;int * 는 int형 변수를 가리키는 pnum1의 선언을 의미함double * pnum2;double * 는 double형 변수를 가리키는 pnum2의 선언을 의미함unsigned int * pnum3;unsigned int * 는 unsigned int형 변수를 가리키는 pnum3의 선언을 의미함

type * ptr;type형 변수의 주소 값을 저장하는 포인터 변수 ptr의 선언

int num1 =5;
double * pnum1 = &num1; //-> 에러. num1 이 정수형이라 포인터 변수의 형도 정수여야 함!!

int main(void) 
{
	int num = 7;
	int * pnum;
	pnum = &num; 
	printf("%d",*pnum);	
}

```

```
int main(void) 
{
	int num = 7;
	int * pnum = &num;
	*pnum = 20; //pnum이 의미하는 변수에 20저장
	//*pnum 은 num을 의미한다
	printf("%d \n" , *pnum)
	
}

```

- 잘못된 포인터 사용과 그것의 예방

```
int main(void)
{
	int * ptr;
	*ptr = 20; ptr 값이 없는 상태에선 쓰레기값이 초기화됨. 따라서 저장되는 위치 알 수 없음

}
```

```
int main(void)
{
	int * ptr;
	ptr = 200; //200이란 대체 어느 저장소 위치인가염...알수없듬. 마찬가지로 위험

}

```
따라서 null포인터로 초기화 하는 것이 바람직하다. int * ptr = NULL; NULL포인터는 0을 의미하는데, 0번지를 뜻하는 것이 아니라, 아무것도 가리키지 않는다는 뜻이다.

###배열과 포인터의 관계

- 배열의 이름은 포인터이다. 하지만 그냥 포인터 변수와의 차이는 주소값의 변경이 불가하다는 것이다. 그리고 앞의 포인터의 속성에서 보았듯이, 포인터가 가르키는 건 시작지점이다. 자료형의 크기에 따라 끝이 결정되기 때문. 배열의 이름도 첫째요소를 가르키는 것. 
- 사실 계속 쓰다보면 헷갈리는 게 좀 있어서 구글링해보는 게 좋은듯 http://iisrc.egloos.com/v/3087711

```

int main(void)
{
	int arr[3] = {1,2,3}; //여기선  int로 선언되었으므로 arr도 int형 포인터변수
	printf("배열의 이름: %p \n", arr);
	printf("첫째요소: %p \n", &arr[0]);
	printf("둘째요소: %p \n", &arr[1]);
	printf("셋째요소: %p \n", &arr[2]);
	//실행해보면 배열요소간 주소 값의 크기는 4바이트임을 알 수 있다
}
```

- 포인터 변수를 이용해 배열의 형태로 메모리 공간에 접속

```

int main(void)
{
	int arr[3] = {1,2,3}; 
	int * ptr = arr; //int * ptr = &arr[0];도 같은 문장
	
	printf("첫째요소: %d %d \n", ptr[0], arr[0]); 
	printf("둘째요소: %d %d \n", ptr[1], arr[1]);
	printf("셋째요소: %d %d \n", ptr[2], arr[2]);
	// 포인터변수를 이용해 배열의 형태로 메모리 공간에 접속
	printf("첫째요소: %d %d \n", *ptr, *arr); //포인터는 처음위치를 가리킴
	}
```

###포인터 연산

```
int main(void)
{
	 int * ptr1 = 0x0010;
	 double * ptr2 = 0x0010;
	 
	 printf("%p %p \n", ptr1+1, ptr1+2);
	 printf("%p %p \n", ptr2+1, ptr2+2);
	 printf("%p %p \n", ptr1, ptr2);
	 ptr1++;
	 ptr2++;
	 printf("%p %p \n", ptr1, ptr2);
	 
}

```
- type형 포인터 변수 대상의 증가 감소 연산 시 sizeof(type)의 크기만큼 값이 증가 및 감소한다.
- int형 포인터 변수의 값은 4씩 증가 및 감소를 하니, int형 포인터 변수가 int형 배열을 가리키면,int형 포인터 변수의 값을 증가 및 감소시켜서 배열 요소에 순차적으로 접근이 가능하다.

```
int main(void)
{
	 int * arr[3] = {11,22,33};
	 int * ptr = arr;
	 
	 printf("%d %d %d \n", *ptr, *(ptr+1), *(ptr+2));
	 printf("%d ", *ptr); ptr++;
	 printf("%d ", *ptr); ptr++;
	 printf("%d ", *ptr); ptr--;
	 printf("%d ", *ptr); ptr--;
	 printf("%d ", *ptr); 
	 return 0
	 
}

```
- 배열이름도 포인터이니, 포인터 변수를 이용한 배열의 접근방식을 배열의 이름에 도 사용할 수 있다. 그리고 배열의 이름을 이용한 접근방식도 포인터 변수를 대상 으로 사용할 수 있다. 결론은 arr이 포인터 변수의 이름이건 배열의 이름이건arr[i] == *(arr+i)

###문자열과 포인터

```
//문자열 선언엔 두 가지 방법이 있다.
int main(void){

char str1[] = "Your team";str1 = "Our team"; //대입 불가. 

char * str2 = "Your team";str2 = "Our team"; // 대입가능
  }

```

- str1은 문자열이 저장된 배열이다. 즉, 문자 배열이다. 따라서 변수성향의 문자열이다. str2는 문자열의 주소 값을 저장한다. 즉, 자동 할당된 문자열의 주소 값을 저장한다. 따라서 상수성향의 문자열이다.
- 뭐 이건 앞에서 배열과 포인터에서 설명한것과 동일 앞에서도 배열을 포인터변수에 할당하면 주소값 바꿀 수 있었지만 배열이름은 주소값을 바꿀 수 없엇음 

- str1 처럼 선언하나 str2 처럼 선언하나, str1, str2 둘 다 문자열의 시작주소를 담고 있는 것은 같다. 

```

char str1[ ] = "My String";
char * str2 = "Your String";

int main(void){
    char str1[ ] = "My String";
    char * str2 = "Your String";
    str1[0] = 'x';
    str2[0] = 'x'; //변경 불가
}

```

- 즉 str1과 같은 문자 배열은, 변수성향의 문자열이고, 구성요소를 바꿀 수는 있지만, 다른 값을 가리키게 할 수는 없다. str2은 그 반대


```
char * str = "Const String";
char * str = 0x1234; // 위의 라인이 실행되면 사실상 다음과 같이 저장되는 것이다
```

###포인터배열

- 포인터 배열 : 포인터 변수들의 배열. 주소값들을 저장할 수 있도록 만든 것!

```
int main (void) {

	int num1 = 10, int num2 = 20, int num3 = 30;
	int * arr[3] = {&num1, &num2, &num3}; //각 변수의 주소값(포인터변수) 저장
	printf("%d \n",  *arr[0]); //*연산자 뜻 알지? 메모리 번지 참조해서 값을 가져와 라는 뜻
	printf("%d \n",  *arr[1]);
	printf("%d \n",  *arr[2]);
	// 프린트 되는 값은 10 20 30
	
}
```

- 문자열을 저장하는 포인터 배열

```
	char * strArr[3] = {"Simple", "String", "Array"}; //문자열 선언
	//큰 따옴표로 묶여서 표현되는 문자열은 그 형태에 상관없이 메모리 공간에 저장된 후 그 주소 값이 반환된다	char * strArr[3] = {0x1004, 0x1048, 0x2012)
	//그니까 실제로는 이렇게 됨	

```
- 느꼈겠지만 문자열은 그냥 배열하고는 또 다르다. 너무 깊게 이해하려고 하지는 말고 그냥 그렇구나 느낌으로 읽어야하겠다.

### 함수와 포인터

- 함수 호출 시 전달되는 인자(argument)의 값은 매개변수(parameter)에 복사가 된다
- 하지만 매개변수로 배열을 선언할 수 없기때문에, 함수 내에서 배열에 접근할 수 있도록 배열의 주소값을 전달하게 할 수 있다.

```
void ShowArayElem(int * param) //int형 포인터변수로 매개변수 설정
//매개변수는 int param[] 이렇게도 설정가능 하다. 하지만 이것은 매개변수 설정에만 그런 것이고
// int arr[3] = {1,2,3};
// int * ptr = arr; 를 int * ptr[] = arr; 이렇게 못함
{
	int i;
	for(i=0; i<len; i++)
		printf("%d ", param[i]);
	printf("\n");
}

int main(void)
{
	int arr1[3] = {1,2,3};
	int arr2[5] = {4,5,6,7,8};
	ShowArayElem(arr1,
}

void AddArayElem(int * Param, int len, int add)
{
	int i;
	for(i=0; i<len; i++)
		param[i] += add;
}

```
- 배열의 값 변경도 가능하다


- Call by value vs Call by reference
- 함수를 호출할 때 단순히 값을 전달하는지, 아니면 주소값을 전달하는지. (전자, 후자)
- 아까 배열을 인자로 전달하는 함수는 Call by reference. 보통 우리가 정의했던 함수들은 Call by value

- Call by reference 함수가 Call by value 함수와 다른 점은 Call by value 함수는 전달받은 인자의 값을 복사해서 함수 결과값을 돌려주지만, 인자 자체에는 손댈 수 없는 반면에 Call by reference는 인자 자체에 접근할 수 있다는 점이다

```
void Swap(int n1, int n2)
{
	int temp = n1;
	n1 = n2;
	n2 = temp;
	printf("n1 n2: %d %d \n", n1, n2);
} 

int main(void)
{
	int num1 = 10;
	int num2 = 20;
	printf("num1 num2: %d %d \n", num1, num2);
	 
	Swap(num1, num2);
	printf("num1 num2: %d %d \n", num1, num2);
	retrun 0

//실행결과
// num1 num2 : 10 20
// n1 n2 : 20 10
// num1 num2 : 10 20 //num1 과  num2는 변하지 않은 것을 볼 수 있다

}
```

- 그러면 어떻게  Swap함수의 결과로 num1 num2 값을 서로 바꿀 수 있지?


```
void Swap(int * ptr1, int *ptr2)
{
	int temp = *ptr1;
	*ptr1 = *ptr2;
	*ptr2 = temp;
} 

```

- 그러면 이제 scanf 함수 호출 시 &연산자붙이는 이유 알겠지? 문자열에 왜 안 붙이는 지도? 문자열이 저장될 배열의 이름은 그 자체로 주소값

```
int main(void)
{
	int num; //num에 사용자 입력값을 대입하기 위해선 주소값을 알아야해 (call by reference)
	scanf("%d", &num)' //변수num의 주소값을 scanf에 전달
}
```

- 포인터 대상의 const 선언

```
int main(void)
{
	int num =20;
	const int * ptr = &num; //포인터 변수 ptr을 이용해서 ptr이 가리키는 변수에 ...
	//저장된 값을 변경하는 것을 허용하지 않는다
	// int * const ptr = &num; 이렇게 하면 포인터변수 ptr이 상수가 된다.
	// 이 말은, 한 번 가리키기 시작한 변수를 끝까지 가리켜야 한다는 것
	* ptr = 30; //컴파일 에러
	num = 40; //컴파일 성공
}


```

```
int main(void)
{
	int num =20;
	int num2 =30;
	int * const ptr = &num; 
	ptr = &num2 //컴파일 에러
	*ptr = 30; //컴파일 성공
	// const int * cosnt ptr = &num; 이렇게 둘 다 선언가능
	//그러면 포인터변수를 사용해서 변수의 값을 바꾸는 거나, 포인터변수를 바꾸는 거나 둘 다 안댐
}


```

### 다차원배열

- 다차원배열에서 주로 거의 다루는 건 2차원 배열. 선언은  Type arr[세로길이][가로길이]; 이렇게 한다

```
int main (void){

	int arr1[3][4]; //세로(행)가 3 가로(열) 4
	printf("세로3 가로4: %d \n", sizeof(arr1)); // sizeof 연산자의 피연산자로
	//배열의 이름이 오면, 배열의 크기가 바이트 단위로 계산되어서 반환됨
	// 여기선 3x4x4 = 48
}
```

- 2차원 배열요소의 접근은 이름이 arr인 int형 배열을 대상으로 N번째 행 M번째 열에 접근하려면 

```
arr[N-1][M-1] = 20; //이런 식으로 접근해서 값을 변경할 수 있다
```

- 2차원 배열의 메모리상 할당 형태 : 컴퓨터 메모리상에서는 1차원으로 저장되어있다!
- 만약 행길이3, 열길이2 인 int형 배열을 0~5로 초기화했다면 arr[0][0], arr[0][1], arr[1][0], arr[1][1], arr[2][0], arr[2][1] 이 각각 값이 0,1,2,3,4,5 인 채로 일렬로 메모리에 저장되어 있다. 배열요소 별 주소값은 int형 변수의 크기인 4바이트만큼 차이. 

- 2차원 배열 선언과 동시에 초기화

```
int arr[3][3] = {{1,0,0},{4,5,0},{7,8,9}};
int arr[3][3] = {1,0,0,4,5,0,7,8,9};
// 두 개 다 같은 matrix 초기화이다.
// 만약 배열의 크기만큼 초기화가 안 되면 부족한 부분은 다 0으로 메꿔진다 (1차원과 마찬가지)

int arr[][] = {1,2,3,4,5,6,7,8}; //에러
//배열의 크기를 알려주지 않고 초기화할 수는 있다. 하지만 위의 예에서 보듯이, 저런 경우
// 2x4 행렬도 될 수 있고, 4x2,8x1,1x8도 될 수 있다.
int arr[2][] = {1,2,3,4,5,6,7,8}; //성공
//이런 식으로 하나만 힌트를 주면 행렬모양이 결정되므로 컴터가 알아서 할 수 있는 것
```

- 3차원 배열은 2차원 배열이 여러 개 모여있는 것으로 생각하면 된다. 필요할 때 관련내용은 찾아보길.

### 포인터의 포인터

- 포인터의 포인터는 포인터 변수를 가리키는 또 다른 포인터 변수를 뜻하는 것으로서, 이중 포인터 또는 더블포인터라 부른다

```
// 이중 포인터의 선언은 다음과 같다
int ** dptr; //int형 이중 포인터 

int main(void)
{
	double num = 3.14;
	double * ptr = &num; // 변수 num의 주소값 저장 
}
// 포인터 변수도 변수이다. 메모리 공간에 할당이 된다. 
// 이 때 이 값을 가르키는 주소값은 double ** dptr = &ptr; 이렇게 저장이 가능하다. 
// 이제 num변수에 접근하는 법이 여러가지가 되었다...!
// *(*dptr) 로 접근할 수도 있고 *ptr로 접근할 수도 있고 그냥 num으로도 접근할 수 있다.
```


- 이중포인터를 이용한Swap 함수 (앞서 포인터와 함수에서 나온 예제)

```
void SwapIntPtr(int **dp1, int **dp2)
{
	int * temp = *dp1;
	*dp1 = *dp2;
	*dp2 = temp;
}

int main(void)
{
	int num1 = 10, num2 = 20;
	int *ptr1, *ptr2;
	ptr1 = &num1, ptr2 = &num2;
	printf("*ptr1, *ptr2: %d %d \n" *ptr1, *ptr2);
	SwapIntrPtr(&ptr1, &ptr2);
	printf("*ptr1, *ptr2: %d %d \n" *ptr1, *ptr2);
	return 0;
	//실행결과
	//*ptr1, *ptr2: 10 20
	//*ptr1, *ptr2: 20 10

}
```

- 포인터 배열의 포인터 형

```
int main(void)
{
	int num1 = 10, num2 =20, num3 =30;
	int *ptr1=&num1;
	int *ptr2=&num2;
	int *ptr3=&num3;
	
	int * ptrArr[] = {ptr1, ptr2, ptr3};
	int **dptr=ptrArr; //대입연산이 가능하다는 것. 즉 ptrArr과 dptr 포인터 형 일치한단거
	
```

###다차원 배열과 포인터

- 1차원 배열이름의 포인터 형은?

ex) int arr[10]; //arr 은 int형 포인터
따라서 함수의 인자로 SimpleFunc(arr); 이렇게 전달되기 위해서는
void SimpleFunc(int*ptr){...} 이렇게 선언되어야 한다

- 2차원 배열의 이름은 그러면 더블 포인터인가?? -> 개소리. 아님

- 예를 들어 int arr2d[3][3]; 우리가 앞에서 계속 봤듯이 arr2d란 배열이름이 가리키는 위치는 배열 중에서도 인덱스 기준으로 [0][0] 즉 제일 첫번째 요소이다. 
- 그런데 2차원 배열은 arr2d[0], arr2d[1], arr2d[2] 도 의미를 갖는다. 각각 1행,2행,3행의 첫번째 요소를 가리킨다.

```
int main(void)
{
	int arr2d[3][3];
	printf("%d \n", arr2d); //4585464
	printf("%d \n", arr2d[0]); //4585464
	printf("%d \n\n", &arr2d[0][0]); //4585464
	
	printf("%d \n", arr2d[1]); //4585476
	printf("%d \n", &arr2d[1][0]); //4585476
	
	printf("%d \n", arr2d[2]); //4585488
	printf("%d \n", &arr2d[2][0]); //4585488
	
	printf("sizeof(arr2d): %d \n", sizeof(arr2d));
	 //sizeof(arr2d): 36  //arr2d대상으로 sizeof연산하면 배열전체 크기 반환
	printf("sizeof(arr2d[0]): %d \n", sizeof(arr2d[0])); 
	//sizeof(arr2d[0]): 12 //arr2d[0]대상으로 할 경우 각 행의 크기 반환
	printf("sizeof(arr2d[1]): %d \n", sizeof(arr2d[1]));
	//sizeof(arr2d[1]): 12
	printf("sizeof(arr2d[2]): %d \n", sizeof(arr2d[2]));
	//sizeof(arr2d[2]): 12
	return 0;
}
```

- 포인터 형에 따라 포인터를 대상으로 하는 증가 및 감소 연산의 결과가 정해진다!

```
int main(void)
{
	int arr1[3][2];
	int arr2[2][3];
	
	printf("arr1: %p \n", arr1); //arr1:004BFBE0
	printf("arr1+1: %p \n", arr1+1); //arr1+1:004BFBE8
	
	printf("arr2: %p \n", arr1); //arr2:004BFBC0
	printf("arr2+1: %p \n", arr1+1); //arr2+1:004BFBCC
	//16진수로 출력되고 있음
}	
```

- arr1을 대상으로 값을 1씩 증가시킬 때마다 8씩증가하고, arr2를 대상으로 값을 1 증가시킨 결과 12가 증가함
- 2차원 배열이름을 대상으로 증가 및 감소연산을 할 경우 연산결과는 각 행의 첫 번째 요소의 주소 값이 된다. 
- 2차원 배열이름의 포인터 형은 가로 길이에 따라서도 달라진다!

예를 들어서 int arr[3][4]; 의 포인터형을 물으면,  배열이름 arr이 가리키는 대상은 int형 변수이고 arr의 값을 1증가하면 실제로는 sizeof(int)x4만큼 주소값이 증가하는 포인터형이다

- 이러한 유형의 포인터 변수 선언은 다음과 같이 한다

예를 들어서 int 형 변수를 가리키면서 포인터 연산시 sizeof(int)x4의 크기단위로 증감하는 포인터 변수ptr은
int(*ptr)[4]; 이다. *로 ptr을 포인터 선언이 되게 한 후 [4]는 4칸씩 건너뛴다는 뜻이며 ptr이 가리키는 변수가 int형이라 int형변수를 4칸씩 건너뛴다는 얘기

- 2차원 배열을 함수의 인자로 전달하기

예를 들면 void SimpleFunc(int (*parr1)[7]) 이런식으로 정의하거나
voidSimpleFunc(int parr1[][7])이런 식으로 선언. 하지만 두 개는 매개변수 선언에서만 같은 것

void ShowArr2DStyle(int (*parr1)[7], int column)
위와 같은 함수의 두 번째 인자가 필요한 이유는 첫번째 인자만으로는 2차원 배열의 세로길이(행길이)를 모르기 때문
배열의 세로길이는 sizeof(arr1) / sizeof(arr1[0]) 이렇게 계산 많이 한다

```
void ShowArr2DStyle(int (*arr)[4]. int column) //배열요소 전체출력
{
	int i, j;
	for(i =0, i<column; i++)
	{
		for(j =0, j<4; i++)
			printf("%d ", arr[i][j]);
		printf("\n");
	}
	printf("\n")
}

void Sum2DArr(int (*arr)[][4]. int column) //배열요소의 합 반환
{
	int i, j, sum =0;
	for(i =0, i<column; i++)
		for(j =0, j<4; i++)
			sum += arr[i][j];
	return sum;
}

int main(void)
{
	int arr1[2][4] = {1,2,3,4,5,6,7,8};
	int arr1[3][4] = {1,1,1,1,3,3,3,3,5,5,5,5};
	ShowArr2DStyle(arr1,  sizeof(arr1) / sizeof(arr1[0]));
	ShowArr2DStyle(arr2,  sizeof(arr2) / sizeof(arr2[0]));
	printf("arr1의 합: %d \n",Sum2DArr(arr1,  sizeof(arr1) / sizeof(arr1[0])));
	printf("arr2의 합: %d \n",Sum2DArr(arr2,  sizeof(arr2) /sizeof(arr2[0])));

	return 0
}

```

- 2차원 배열에서도 arr[i]와 *(arr+i)는 같다

###함수포인터와 void 포인터

- 프로그래머가 정의하는 모든 함수는 프로그램 실행 시 메인 메모리에 저장되어서 실행된다. 
- 함수의 이름은 메모리상 저장된 함수의 주소 값이다 (배열과 마찬가지)
- 함수의 이름도 상수이다 (배열과 마찬가지)
- 함수의 주소 값 저장을 위해 포인터 변수를 별도로 선언할 수 있고 이렇게 선언된 변수가 함수포인터변수
- 함수의포인터변수의 형은 반환형과 매개변수의 선언형태를 기준으로 구분
- int(*fptr)(int) 이렇게 선언한다
- 그리고 이 함수 포인터 변수에 함수SoSimple의 주소값을 저장하려면 fptr = SoSimple;
- 이후에는 동일하게 호출가능 ftpr(3,4);

```
int WhoIsFirst(int age1, int age2, int (*cmp)(int n1, int n2))
{
	return cmp(age1,age2);
}
```

- 형이 존재하지 않는 void 포인터
- void * ptr; 이렇게 선언
- void 포인터는 형이 정해져 있지 않아서 연산도 못하고 값 변경, 참조도 못한다.


## 구조체

- 구조체는 하나 이상의 변수를 묶어서 새로운 자료형을 정의하는 도구

```
struct point 
{
	int xpos;
	int ypos;
};
// 이렇게 정의된 struct point란 자료형을 바탕으로 새로운 변수를 생성할 수 있다.

struct point pos // pos라는 이름의 구조체 변수 선언
pos.xpos = 20; //구조체 변수 pos의 멤버 xpos에 20을 저장

//구조체 정의와 동시에 변수선언
struct point 
{
	int xpos;
	int ypos;
}pos1,pos2,pos3;

struct point 
{
	int xpos;
	int ypos;
};
struct point pos1,pos2,pos3 //구조체 변수의 선언

//구조체 변수의 초기화
struct point pos = {10,20} //멤버 순서대로 초기화

//구조체변수선언 이후에 구조체 멤버에 문자열 저장하기 위해선 strcpy함수 필요
//하지만 초괴화과정에서는 불필요

struct person
{	
	char name[20];
	char phoneNum[20];
	int age;
};

struct person man1;
strcpy(man1.name, "안성준");

struct person man2 = {"이승기","010-3030-2039",12};
```

### 구조체와 배열 그리고 포인터

- 구조체 배열의 선언과 접근

별 거 아니고 구조체 변수들의 배열을 만드는 것. struct point arr[4];와 같이 선언. 배열의 두번째 요소의 멤버에 접근하고 싶다면 arr[1].xpos 이렇게 접근

- 구조체 배열의 초기화

```
struct person arr[3] = { {"이승기","010-3030-2039",12},  {"김위백","010-3453-2039",27}, {"조수희","010-9879-2039",23}}
```

- 구조체 변수와 포인터

```
struct point pos = {11,12};
struct *pptr = &pos; //포인터변수 pptr이 구조체 변수 pos를 가리킴
// 포인터변수니까 *를 이용해서 변수에 접근가능
(*pptr).xpos =10; // pptr이 가리키는 구조체 변수의 멤버 xpos에 10저장
//* 연산과 . 연산을 한방에 하는 방법이 있다
pptr->xpos = 10; //이것은 위와 같은 연산이다.

```

- 포인터 변수를 구조체의 멤버로 둘 수 있다.

```
struct point
{
	int xpos;
	int ypos;
};

struct circle
{
	double radius;
	struct point * center;
};

int main (void)
{
	struct point cen = {2,7};
	double rad = 5.5;
	
	struct circle ring = {rad, &cen};
	printf("원의 반지름: %g \n", ring.radius);
	printf("원의 중심: [%d, %d] \n", (ring.center)->pos, (ring.center)->ypos);
	return 0;
}

```

- Type형 구조체 변수의 멤버로 Type형 포인터 변수를 둘 수 있다

이로써 같은 타입의 구조체 변수들 끼리 연결이 가능하다!

```
struct point
{
	int xpos;
	int ypos;
	struct point * ptr; //구조체 point의 포인터 변수 선언
};
```

### 구조체의 정의와 typedef선언

- 구조체 변수 선언 시에는 무조건 struct 선언이 추가 되어야 한다. 예를 들어서 struct person man 이렇게. 근데 앞의 struct 선언을 하기가 너무나 귀찮은 것이다. 그냥 person man 하고 싶은 것이다. 이 때 먼저 구조체를 정의한 뒤에 typedef를 추가하면 된다

- typedef선언 기존에 존재하는 자료형의 이름에 새 이름을 부여하는 것을 목적으로 하는 선언. 새로운 이름의 부여는 가장 마지막 단어에 의해 이루어진다.

예를 들면 typedef name1 name2 name3; 에서 가장 마지막의 name3 가 'name1 name2'에 부여된 새로운 이름이 되는 것이다. 

```
typedef unsigned int UNIT; // unsigned int 에 UNIT이란 이름 새로 부여!

struct point
{
	int xpos;
	int ypos;

};

typedef struct point Point; //이제부터 struct point 데이터 타입을 Point라 하겠다

Point pos; // Point 타입의 pos 변수가 선언 

typedef struct point //이런식으로도 선언가능. 
{
	int xpos;
	int ypos;

};

typedef struct {
	int xpos;
	int ypos;

}Point; //구조체의 이름은 이제 필요하지 않다. 어차피 Point란 새로운 이름이 생겼으니!

```

- 함수로의 구조체 변수 전달과 반환


```
typedef struct {
	int xpos;
	int ypos;

}Point;

void ShowPosition(Point pos) //구조체인 매개변수를 다음과 같이 받는다
{
	printf("[%d, %d] \n", pos.xpos, pos.ypos);
} 

Point GetCurrentPostion(void) //구조체를 반환하는 함수이다
{
	Point cen;
	printf("Input current pos: ");
	scanf("%d %d", &cen.xpos, &cen.ypos);
	retrun cen;
}

//여기에서 정의된 함수들은 CallbyValue임을 잊지말자. 메모리주소(포인터)값을 전달하지 않는 경우 모두 CallbyValue. 즉 매개변수로 들어온 값들을 복사해서 함수 내에서 쓰는 것
```

- 구조체 변수를 대상으로 가능한 연산 : 대입연산(복사해서 값 집어넣기) , &연산, sizeof연산 정도.
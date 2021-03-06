<br/> 

###### Top

  - [컴퓨터는 왜 이진법을 사용하는가?](#컴퓨터는-왜-이진법을-사용하는가)


  - [언어분류](#언어분류)
    - [언어수준(저수준언어, 고수준언어)](#언어수준저수준언어--고수준언어)
    - [타입별(강한타입, 약한타입)](#타입별강한타입-약한타입)
    - [처리수준(컴파일언어, JIT컴파일언어, 인터프리터)](#처리수준컴파일언어--jit컴파일언어--인터프리터)
    - [메모리관리(매니지드, 언매니지드)](#메모리관리매니지드-언매니지드)

  - [프로그래밍 패러다임(절차적언어, 개체지향 언어[OOP])](#프로그래밍-패러다임절차적언어-개체지향-언어oop))
  - [프레임워크, 라이브러리](#프레임워크-라이브러리)
  - [디버그(debug)빌드, 릴리즈(release)빌드](#디버그debug빌드-릴리즈release빌드)
  - [컴파일(Compile)](#컴파일compile)
  - [자료크기](#자료크기)
  - [값형, 참조형](#값형-참조형)
  - [접두사](#접두사)
  - [형변환](#형변환)
  - [이스케이프문자](#이스케이프문자)

  - [진수](#진수)
    - [진법](#진법)
    - [8진법, 16진법, 32진법](#8진법-16진법-32진법)
    - [진수변환](#진수변환)
    - [비트,바이트](#비트바이트)
    - [비트, 음수와 양수의 관계 및 수의표현, 및 최하위 비트로 짝수 홀 수 판단](#비트-음수와-양수의-관계-및-수의표현-및-최하위-비트로-짝수-홀-수-판단)
    - [비트마스킹(bit masking)](#비트마스킹bit-masking)

  - [연산자](#연산자)
    - [증감 연산자](#증감-연산자)
    - [비트이동연산자](#비트이동연산자)
    - [비트연산자](#비트연산자)

  - [음수-표현법](#음수-표현법)
  - [문자인코딩](#문자인코딩)
  - [유리수표현법](#유리수표현법)
  - [불대수](#불대수)
  - [빅오 표기법(시간복잡도)](#빅오-표기법시간복잡도)
  - [알고리즘](#알고리즘)
  - [자료구조](#자료구조)
  - [기타, 도움링크](#기타-도움링크)

<br/>

***
***

<br/>

## 컴퓨터는 왜 이진법을 사용하는가?
  - 하드웨어 적으로 컴퓨터는 '전기가 흐른다 1', '전기가 흐르지 않는다 0'라는 두가지 상태밖에 없기 때문
  - 2진법을 사용

###### [Top](#top)

<br/>

***

<br/>

# 언어분류

###### [Top](#top)

## 언어수준(저수준언어 , 고수준언어)
  - 컴퓨터가 이해하지 쉬운 언어에 가까울수록 저수준 언어
    - 0과1로만 이루어짐(= 기계어)
  - 인간이 이해하기 쉬운 언어에 가까울수록 고수준
    - 어셈블리어, C, C++ 등등
      - 어셈블리어는 기계어와 1:1대응하는 언어기 때문에 사실상 저수준 언어..(다른 언어는 1:1대응이 아님)
  - 언어의 수준은 상대적인 부분이 있음(ex 어셈블리어는 C 보다 상대적으로 저수준 언어)

###### [언어분류](#언어분류)

<br/><br/>

## 타입별(강한타입, 약한타입)
  - 타입검사에 엄격한가, 엄격하지 않은가에 대한것. 컴퓨터가 이해하는 데이터는 수로 이루어져 있기 때문에 사람 입장에서는 그 수만 보아서는 실제로 정수를
의미하는지 문자열을 의미하는지 알 수가 없기 때문에 타입지정이 생겨났음.따라서 강한타입일 수록 타입 검사에 엄격하기 때문에 추후에 생길 버그나 오류를 줄 일 수 있다.
  - ex) 파이썬 같은 경우는 변수형을 비선언 한다.

###### [언어분류](#언어분류)

<br/><br/>

## 처리수준(컴파일언어 , JIT컴파일언어 , 인터프리터)
  - 컴파일언어(코드 - 컴파일[기계어로 바꿔줌] - 기계어[실행파일로 바꿔줌 exe파일] - 실행)
    - 실행만 할 경우 마지막 두 단계만 왔다 갔다 하는것
    - 코드를 바꿔야 할 경유 처음부터 순서를 밟아 다시 진행한다
    - 다양한 최적화 가능(2시간 동안 컴파일, 0.1초 만에 실행)
    - 기계어가 나오기 때문에(다른 CPU에서 이해 불가능) 플랫폼마다 다른 exe파일을 컴파일 해야함
    - C, C++
  - JIT컴파일언어(코드 - 컴파일러[중간언어로 바꿔줌] - 중간언어["exe" <- 실행 파일이라고 하기 뭐함..] - JIT컴파일러(기계어) - 실행)
    - 프로그램 실행 중에 VM이 중간 언어를 기계가 이해하는 언어로 바꿔서 실행
    - 플랫폼 별로 VM(가상머신)을 설치해야함
    - 플랫폼에 종속적이지 않고 VM에 종속적임
    - C#, Java 등
  - 인터프리터언어(코드 - 인터프리터[기계어로 바꿔줌 <- 실행하면서 실시간으로 바꿔줌] - 실행)
    - 실제로 실행하기 전까지 코드의 문제를 잡아낼 수 없음

###### [언어분류](#언어분류)

<br/><br/>

## 메모리관리(매니지드, 언매니지드)
  - 매니지드 언어 : 언어가 메모리를 관리해줌
    - 언어가 자체적으로 모든 상황에서, 충분한 판단으로 메모리를 반환하기 때문에 명시적으로 반환하는 것보다 효율적이지 않음
  - 언매니지드 언어 : 언어가 메모리를 관리 안해줌
    - 명시적으로 메모리를 반환하기 때문에 효율적임
    - 프로그래머가 신경써 줘야 되기 때문에 실수가 나올 수 있음
    - 성능이 필요할 경우에 사용
    - 메모리동작원리, CPU동작원리, 컴퓨터처럼 생각하는 방법, 매니지드 언어에서 지원하는 마법같은 기능의 동작원리 등을 알 수 있고 이해할 수 있게 된다.

###### [언어분류](#언어분류)

<br/>

***

<br/>

## 프로그래밍 패러다임(절차적언어, 개체지향 언어[OOP])
  - 절차적 언어 : 순서에 따라 위에서 부터 아래로 절차적으로 코드를 실행하는 것. 컴퓨터의 처리구조와 유사해 속도가 빠름
  - 개체지향 언어(클래스) : 기능과 자료를 하나의 개체에 합침
    - 사람에게 직관적. ex)사물을 볼때 하나의 정보만 보는 것이 아니라 컬러,질감,모양,무게 등 다양한 정보로 하나의 사물을 바라봄
    - 복잡한 프로그램의 구조를 잡기 쉽다, 재사용성 증가, 변형가능성을 높일 수 있음

###### [Top](#top)

<br/>

***

<br/>

## 프레임워크, 라이브러리
  - 라이브러리 : 여러 함수들을 모아 놓은 집합. 프로그래머가 필요할때 가져와서 대체해 사용할 수 있음
  - 프레임워크 : 라이브러리의 상위 개념, 제공받은 일정한 요소와 틀, 규약을 가지고 무언가를 만들어 낼 수 있음
  - 라이브러리와 프레임워크의 차이는, 라이브러리는 필요할때 필요한 함수를 프로그래머가 불러다가 쓸 수 있지만, 프레임워크는 프로그래머가 부르는 것이 아니라, 프로그래머가 그 안에 들어가 일정한 틀과 규약을 준수 하면서 개발을 해날갈때 쓰는 도구 같은것.
  - C#은 최상단에 'Using'지시어 뒤에 사용할 라이브러리(= 네임 스페이스 라고도 부름) 이름을 넣는다.

###### [Top](#top)

<br/>

***

<br/>

## 디버그(debug)빌드, 릴리즈(release)빌드
  - 디버그빌드 : 개발자가 개발 중에 사용하는 실행파일
    - 디버깅에 유용한 많은 정보가 담겨 있음
    - 성능 떨어짐
  - 릴리즈빌드 : 실제 사용자에게 배포하는 실행파일
    - 디버깅을 위한 정보는 빠지게 됨
    - 성능 빠름

###### [Top](#top)

<br/>

***

<br/>

## 컴파일(Compile)
  - 소스코드를 기계 또는 VM(Virtual Machine)이 이해할 수 있는 언어로 변경하는 행위
    - 컴파일로(compiler)라는 프로그램이 진행해줌 ex)IDE(통합개발 환경)
    - 컴파일 할때 오류또는 경고가 발생할 수 있음

###### [Top](#top)

<br/>

***

<br/>

## 자료크기
  - 비트(bit) : 최소단위 1혹은0을 담을 수 있음
  - 바이트(byte) : 8비트가 모인것
  - 1024바이트 = 1킬로 바이트(KB)
  - 1024킬로바이트 = 1메가 바이트(MB)
  - 기가,테라,페타....

<br/>

  - 하지만 현재 판매하고 있는 하드디스크, 네트워크, 인터넷망 등은 1000바이트 = 1킬로 바이트, 1000킬로바이트 = 1메가 바이트 이렇게 되어 있음. 그래서 1GB외장 하드를 구매 해서 컴퓨터에서 본다면 데이터를 잃어 버리는 격이 된다.(하드디스크 : 1GB = 1,000,000,000바이트, 컴퓨터 : 1,000,000,000 / 1024 / 1024 / 1024 = 0.931GB)

###### [Top](#top)

<br/>

***

<br/>

## 값형, 참조형
  - 값형 : 자신이 직접 데이터를 저장해서 보관하는 자료형(스택 영역에 저장)
    - 스택은 메모리에 아래서부터 데이터가 쌓였다가 데이터가 제거될 때는 맨 위에 있는 데이터부터 차례로 제거되는 방식이다
  - 참조형 : 데이터가 저장되어 있는 힙의 위치만 자신이 저장하고 있다가 필요할 때 그 데이터가 있는 곳으로 가서 데이터를 얻어오는 자료형(힙 영역에 저장)  
    - 힙은 쌓여 있는 구조가 아니라, 임의의 메모리에 데이터를 저장한다. 그러한 특성 때문에 힙은 자유 기억 공간이라고도 한다

###### [Top](#top)

<br/>

***

<br/>

## 접두사
  - 0b- : 2진수 ex) int num1 = 0b10  //이때 num1에 들어가는 수는 2가됨
  - 0x- : 16진수 ex) int num1 = 0x10 //이때 num1에 들어가는 수는 16이됨  

###### [Top](#top)

<br/>

***

<br/>

## 형변환
  - 묵시적 변환 : 컴파일러가 '알아서' 해주는것
    - 모든 자료형을 바꿀 수 있는 것은 아님
  - 명시적 변환 : 프로그래머가 명시적으로 형변환을 지시함(전부x)
  - 승격 : 컴파일러가 자동으로 실수형이나 부동소수형 자료의 이진 표현을 확장 하는것
    - double num1 = 5.5, int num2 = 3 / num1 + num2 = 8.5가 나오게 된다. double로 승격하여 계산 한것
      - [꼼수 : 승격을 이용하여double number = 123.456 을 소수점 첫째 자리만 나타내기
](https://github.com/BuMinKyoo/TIL/tree/main/C%23/%EA%BC%BC%EC%88%98...)

###### [Top](#top)

<br/>

***

<br/>

## 이스케이프문자
  - \n -> 줄바꿈
  - \t -> 탭
  - \' -> 작은따옴표 출력
  - \" -> 큰따옴표 출력
  - \\ -> 백슬래시 출력
  - \x(숫자) -> 아스키값16진수 출력 ex) \x120출력 -> ?가 출력됨

###### [Top](#top)

<br/>

***

<br/>

# 진수

###### [Top](#top)

## 진법
  - 수를 표현하는 방법
  - 2진법, 8진법, 10진법, 16진법 등
  - ex) 2진법 : 2개의 숫자를 사용하여 수를 표현하는 방법 => 표현법 0b (0,1)
  - ex) 16진법 : 16개의 숫자를 사용하여 수를 표현하는 방법 => 표현법 0x (1,2,3,4,5,6,7,8,9,A,B,C,D,E,F)

###### [진수](#진수)

<br/><br/>

## 8진법, 16진법, 32진법
  - 비트는 단위가 작아서 비트 8개 모인 바이트를 기본 단위로 사용하게 되는데, 8진법이나, 32진법 같은 경우 비트수 3개, 5개 이기 때문에 메모리 단위로 데이터를 저장하기에는 딱딱 끊어지지 않아서 적합하지는 않는다. 그에 비해서 16진법은 비트수4개로(1바이트에 16진수 자리는 2개) 잘 들어맞기 때문에 적합하다고 할 수 있다

###### [진수](#진수)

<br/><br/>

## 진수변환
  - 10진수 -> 다른진수 바꿀때, 10진수 수를 다른진법에 해당하는 수로 나누어서 나머지쪽 부터 확인하면 됨

10진수 -> 2진수
<img src="https://user-images.githubusercontent.com/39178978/155839336-a1ef1e91-29be-4e67-be07-40d3033794f8.jpg" width="250" height="350">

<br/>

10진수 -> 8진수
<img src="https://user-images.githubusercontent.com/39178978/155839339-cf8fdeaf-9b35-44f3-b043-fb04b08722ed.jpg" width="250" height="350">

<br/>

  - 2진수 -> 8진수 : 2진수를 세 자리씩 끊어서 8진수 한자리로 변환
  - 8진수 -> 2진수 : 8진수 한 자리를 2진수 세자리로 변환

<img src="https://user-images.githubusercontent.com/39178978/155839708-eb10184a-2afb-470e-9e08-e393bb5cf27d.jpg" width="250" height="350">

  - 2진수 -> 16진수 : 2진수를 네 자리씩 끊어서 16진수 한자리로 변환
  - 16진수 -> 2진수 : 16진수 한 자리를 2진수 네자리로 변환

<img src="https://user-images.githubusercontent.com/39178978/155839703-3b9e8489-f6fd-4482-a5f2-afe51fa010d1.jpg" width="250" height="350">

<br/>

  - 8진수 -> 16진수 : 2진수를 거쳐서 변환 하는것이 편함

###### [진수](#진수)

<br/><br/>

## 비트,바이트
  - 비트 : 컴퓨터의 구성요소인 트랜지스터에 전기가 흐르면 1, 흐르지 않으면 0 으로, 트랜지스터의 상태를 기록하는 최소 단위를 비트라고 한다
  - 바이트 : 비트가 8개 모인 데이터

###### [진수](#진수)

<br/><br/>

## 비트, 음수와 양수의 관계 및 수의표현, 및 최하위 비트로 짝수 홀 수 판단
  - 비트당 표현 가능한수 2가지, 즉 2의 n승가짓수로 표현 가능
  - 부호 있는 자료형은 양수에서 0을 포함함으로 범위로는 음수가 1개소 더 많이 표현 가능
    - ex) sbyte인 경우 8비트 이기 때문에 표현 가능한 수는 2의 8승으로 256가짓수. 0을 양수에 포함 시키고 절반씩 나누게 되면 음수는 128가지 양수는 0을 제외한 127가지, 즉 [-128~127]까지의 수를 표현 가능
    - ex) ㅁㅁㅁㅁㅁㅁㅁㅁ 8개의 비트가 있다면 맨 위쪽의 최상위 비트 가짓수가 나머지 표현 가능한 비트의 수많큼이 되므로, 음수는 최상위 비트가 1로 표현 된다고 볼 수 있다.
    - 자료형의 크기보다 크기가 커지거나 작아지면 '오버플로우' 또는 '언더플로우'가 발생한다
    - 최하위 비트가 0이면 짝수, 1이면 

###### [진수](#진수)

<br/><br/>

## 비트마스킹(bit masking)
  - 각각의 비트에 하나의 기능을 만든후, 그것을 키고 끄고 하는식으로 이용
  - 하나의 비트만을 켜고 싶을 경우
    - 어떤수에 |(비트 합 연산)을 하고, 켜고 싶은 비트만을 1 로 해두기 ex) 0b0000 1000
  - 하나의 비트만을 끄고 싶을 경우
    - 어떤수에 &(비트 곱 연산)을 하고, 끄고 싶은 비트만을 0 으로 해두기 ex) 0b1111 0111
  - 특정 비트 토글하기
    - 어떤수에 xor연산을 하고, 토글 하고 싶은 비트만을 1 로 해두기 ex) 0b0000 1000

###### [진수](#진수)

<br/>

***

<br/>

# 연산자

###### [Top](#top)

## 증감 연산자
  - 증감 연산자(++ , --)
    - 증감 연산자가 앞쪽에 있으면 증감 해주고 계산
    - 증감 연산자가 위쪽에 있으면 계산후 증감

~~~c#
int num = 0;
Console.WriteLine(++num + ++num + ++num); // 6
~~~

~~~c#
int num = 0;
Console.WriteLine(num++ + num++ + num++); // 3
~~~

###### [연산자](#연산자)

<br/><br/>

## 비트이동연산자
  - 비트이동연산자(<<[왼쪽으로이동], >>[오른쪽으로이동])

~~~c#
int num = 1; //num = 0b0001
int num2 = num << 3; //num2 = 0b1000
Console.WriteLine(num2); //num2 = 8
~~~

###### [연산자](#연산자)

<br/><br/>

## 비트연산자
  - 비트연산자(&[and], |[or], ^[xor], ~[not])
  - 연산자 우선순위 : & -> ^ -> |

~~~c#
0b0011 & 0b0010 => 0b0010
0b0011 | 0b0010 => 0b0011
0b0011 ^ 0b0010 => 0b0001
~0b0011 => 0b1100
~~~

  - xor 연산자로 두수 바꾸기

~~~c#
static void Main(string[] args)
{
    int a = 3;
    int b = 8;

    a = a ^ b;
    b = b ^ a;
    a = a ^ b;

    Console.WriteLine($"a : {a}, b : {b}");
}

출력
a : 8, b : 3
~~~

###### [연산자](#연산자)

<br/>

***

<br/>

## 음수 표현법
  - 공부한 블로그 링크 : https://st-lab.tistory.com/189 
  - 부호 절대값(Sign-Magnitude) : 컴퓨터 세계에서 부호를 붙이기 위해서 8비트의 최상위 비트가 0이면 양수, 1이면 음수로 지정하게 됨
    - 단점
      - +0과, -0둘다 존재하는것
      - 양수+양수 덧셈은 문제가 없지만, 음수+양수, 양수+음수, 음수+음수를 할때 각 상황마다 다르게 고려해야 된다.

<img src="https://user-images.githubusercontent.com/39178978/155979686-84fee69b-40e6-4c00-b021-39c656c943ed.png"/>

  - 1의 보수 (One's Complement)
    - ex) 7에 대한 10의 보수 : 7 + 3 = 10 => 3 / 17에 대한 10의 보수 : 17 + 83 = 100 => 83
    - ex) 7에 대한 9의 보수 : 7 + 2 = 9 => 2 / 17에 대한 9의 보수 : 17 + 92 = 99 => 82
    - ex) 10의 보수를 이용한 계산(-20+45) : (100-20)+45-100 => 80+45-100 => 125-100(올림이 발생하니 버림) = 25
    - ex) 0000 0011에 대한 1의 보수 : 0000 0011 + 1111 1100 = 1111 1111 => 1111 1100(음수는 양수의 비트를 반전시킨 값)
    - 8비트짜리 정수일경우 0과 +0이 존재 하기 때문에 수의 범위는 [-127,127]
    - 단점
      - +0과, -0둘다 존재하는것
      - 계산시 캐리가 발생하면 +1을 해줘야함

<img src="https://user-images.githubusercontent.com/39178978/155984631-d0175195-6254-4aa8-99cf-86a2675d8f4c.png"/>

  - 2의 보수 (Two's Complement)
    - 1의 보수에서 사용하면 -0(1111 1111)을 없애고 -1씩 대응시키게됨
    - 어떤 수의 부호를 바꾸고자 하면 비트를 반전시키고 거기에 1을 더하면됨
    - 부호 절대값과 1의 보수에 있었던 문제를 모두 해결하게 됨
    - 8비트짜리 정수일 경우 0이 하나만 존재 하기 때문에 수의 범위는 [-128,127]
    - 장점
      - 0이 1개 밖에 없음
      - 캐리가 발생해도 +1을 하지 않아도 됨
      - 양수+양수, 양수+음수, 음수+양수, 음수+음수의 모두 계산이 문제가 없음

<img src="https://user-images.githubusercontent.com/39178978/155987419-97bcb7b8-b958-41b7-8039-c88b5ca37a2c.png"/>

###### [Top](#top)

<br/>

***

<br/>

## 문자인코딩
  - 아스키(ASCII)
    - 영어 알파펫과 기호들을 컴퓨터에서 표현하는 규약
    - 최초의 아스키는 총 128개의문자를 표현(7비트사용, 1비트는 오류 검증으로 사용)
    - 영어권에서는 주로 아스키를 사용함(영어와, 특수문자가 들어가 있기 때문)
  - ANSI(Windows-1252, CP-1252)
    - ASCII의 확장판
    - 영어뿐만 아니라 다른 라틴문자 기반의 언어를 표시하기 위해 만든 문자 인코딩
    - 256개의 문자를 표현(8비트를 모두사용) => 하지만 이렇게 해도 세상의 모든 언어를 표시 할 수 없기 때문에 CodePage개념이 추가됬다.
    - ANSI = ASCII Code(7bit) + CodePage(1bit)
  - 멀티바이트(Multibyte)
    - 표기할 문자가 많은, 1바이트에 담을 수 없는 언어들을 위해서 나옴
    - 기본적으로 아스키코드에 들어가 있는 1바이트(영문,숫자,기본적인 특수문자)는 그대로 가고, 그다음에 더 필요한 문자들을 채워 넣음
    - ex) EUC-KR, EUC-CN, EUC-TW 등등...
    - 여러 언어를 한번에 표현 하지 못하기 때문에, 한페이지에 다른 나라 언어가 적혀 있으다면 동시에 표현이 안됨
  - 유니코드(Unicode)
    - 전 세계의 모든 문자 및 이모지까지 '일관되게'표현할 수 있는 규격
    - 2021년09월14일에 Unicode 14.0이 나왔고 144,697문자를 표현한다, 지금도 계속 늘려 가고 있음
    - UTF-8(1바이트), UTF-16(2바이트), UTF32(4바이트) : 한글자를 저장할때 몇바이트를 쓸건지 명시하는것
 
 <br/>
 
  - UTF-8
    - 아스키 코드와 100% 호환
    - 바이트 정렬(엔디언)문제가 발생하지 않음
    - CJK(중국,일본,한국)를 제외한 거의 모든 문자에 1바이트 또는 2바이트를 사용
      - 한국어는 대부분 3바이트가 필요함 => UTF-16을 쓰면 대부분 2바이트로 표현 가능
    - UTF-8은 1바이트, 즉 8비트 이다, 유니코드상 표기가 높은 수쪽에 있는 한국어의 경우 UTF-8로 인코딩 했을시 2바이트 또는 3바이트가 필요하기 때문에, '비트 패턴을 넣어서 이 글자가 몇 바이트로 인코딩 되고 있는지'를 알려 주어야 한다. => 따라서 몇개의 비트수를 낭비하지만 4바이트까지 총 21개 비트를 표현 할 수 있다.(2,097,152개 표현)

<img src="https://user-images.githubusercontent.com/39178978/156084310-07986758-02a3-48a4-bab5-dbda2e15edd3.png"/>

  - UCS-2
    - 고정 2바이트 인코딩

  - UTF-16
    - 인코딩/디코딩 규칙이 복잡
    - 엔디언 문제 ex)리틀 엔디언으로 저장했는데 빅 엔디언으로 읽으면 잘못된 결과 나옴
    - 아스키와 호환 안됨

  - UTF-32
    - 유니코드 code point와 1:1대응
    - 용량 낭비가 심함
    - 아스키와 호환 안됨
    - 엔디언 문제 있음

###### [Top](#top)

<br/>

***

<br/>

## 유리수표현법
  - 10진법 실수  550.337 = 500 + 50 + 0 + 0.3 + 0.03 + 0.07

<img src="https://user-images.githubusercontent.com/39178978/156096606-5d286196-a5f5-4165-9bbc-05431083b942.png"/>

<br/>

  - 2진법 실수 101.011 = 4 + 0 + 1 + 0/2 + 1/4 + 1/8

<img src="https://user-images.githubusercontent.com/39178978/156096940-4a6397b9-14a9-479d-98da-cb4414ba8a50.png"/>

<br/>

  - 실수의 10진수 -> 2진수 변환
    - 11.8125 = 1011.1101(2진수) => [8  4  2  1 . 0.5  0.25  0.125  0.0625]
    - 10진수 0.1을 2진수로 바꾸려고 하면 나누어 떨어지지 않기 때문에 정확하게 표현 되지 못한다.

<img src="https://user-images.githubusercontent.com/39178978/156138197-24e8bfb0-a508-41ac-922e-fda36f809007.png" width="250" height="500"/>

<br/>

  - 고정 소수점 수
    - 언제나 정해진 자리에 소수점이 찍혀 있다는것
    - 8비트를 예로 들면, 부호비트로 1개소, 정수부분 4개소, 소수부분 3개소로 표현 한다면 기호로 Q4.3이라고 표현 함
    - 표현할 수 있는 범위의 값은 확실히 표현 가능(오차가 없어야 하는 제품에 적합)
    - 표현 가능한 범위가 작아짐

  - 부동 소수점 수
    - 소수점 자리가 정해져 있지 않다
    - 돈 관련되서는 사용하는데 부적합함 => 하지만 다른곳에 사용하는데는 큰 문제는 없음 ex) 0.001m잘못 움직였다고 일반적으로 큰일이 나지 않음
    - 표현 가능한 범위가 넓음
    - IEEE 754표준을 따름

  - IEEE 754표준(32비트 부동 소수점)
    - 부호비트 : 1비트 / 지수비트 : 8비트 / 가수비트 : 23비트
    - 정규화 작업 : 110.110111 => (+1) * 1.10110111 * 2의2승 / -0.00123 => (-1) * 1.23 * 2의마이너스2승
    - 음수를 표현할때 부호 절대값 방식을 사용함
    - ex) 234.48 => 11101010.0111101011100001 = 1 * 1.11010100111101011100001 * 2의7승
      - 부호비트 = 0
      - 지수비트 : 10000110(7+127 = 134)
      - 가수비트 : 11010100111101011100001
    - ex) -234.48 => 11101010.0111101011100001 = (-1) * 1.11010100111101011100001 * 2의7승
      - 부호비트 = 1
      - 지수비트 : 10000110(7+127 = 134)
      - 가수비트 : 11010100111101011100001
    - ex) 3.14 => 11.0010001111010111000011 => 1 * 1.10010001111010111000011 * 2의1승
      - 부호비트 : 0
      - 지수비트 : 100000000(1+127 = 128)
      - 가수비트 : 10010001111010111000011
      - 0 100000000 10010001111010111000011 => 10진수 변한 => 지수 : 128 - 127 = 1 / 가수 : 10010001111010111000011 = 1.10010001111010111000011 => 1.10010001111010111000011 * 2의1승 = 11.0010001111010111000011 => 3.1400001049041748046875 => 값이 오차가 생김!
    - float 정밀도 : 6 ~ 9자리 / double 정밀도 : 15 ~ 18 <= 범위가 있다는 것이 이상한데 그 이유를 아래에 설명
      - float 정밀도 : 6자리 : 10진수 실수를 float(double)에 저장했다가 다시 그걸 10진수 실수로 변환한뒤, 원래 10진수 실수와 동일한 유효 숫자로 맞출 때 원래 값이 그대로 나올 수 있는 최대 유효숫자 수는 6자리이다
      - float 정밀도 : 9자리 : 서로 다른 수가 정말 다르다는 걸 알려면 최대9번째 유효숫자까지 확인해야 한다는것

~~~c#
//float 정밀도 : 6자리

static void Main(string[] args)
{
    long i = 123456000000000;
    float f = i;
    i = (long)f;
    Console.WriteLine(i);
}

출력
123455999574016 <= 6자리 그 다음에 7번째에서 반올림 하면 123456이 나오게됨. 그러므로 어떤 유효숫자 다음의 수는 그 유효숫자가 되기 위한 근접 수로 표현 하게됨
~~~

###### [Top](#top)

<br/>

***

<br/>

## 불대수
  - 드 모르간의 법칙 => 전체를 뒤집으면 결과가 같음
  - if(!(age >= 20 && height >= 140)) = if(age < 20 || height < 140)
  - if (!(student.Age < 25 || student.TermNum == 2)) = if(student.Age >= 25 && student.TermNum != 2)

###### [Top](#top)

<br/>

***

<br/>

## 빅오 표기법(시간복잡도)
  - O(1) : 반복문이 없음, 상수 => 오직 한 단계만 거침
  - O(log n) : 분할 알고리즘 ex)이진탐색 => 필요한 단계들이 연산마다 특정 요인에 의해 줄어듬 
  - O(n) : for문 하나
  - O(n^2) : 이중 for문 => for문이 밖에 있으면 2n이됨
  - O(2^n) : 피보나치
  - O(n!) : 모든 도시를 단 한번만 방문한 뒤 다시 첫 도시로 돌아오는 경로, 완전탐색

<img src="https://user-images.githubusercontent.com/39178978/156878962-9f1d688b-9d06-40cd-ae2b-918bb9040f24.png" width="600" height="350"/>

###### [Top](#top)

<br/>

***

<br/>

## 알고리즘
  - 자료구조에 쌓인 데이터를 활용해 어떤 동작들을 만들어 가는것

###### [Top](#top)

<br/>

***

<br/>

## 자료구조
  - 데이터를 원하는 규칙 또는 목적에 맞게 저장하기 위한 구조
 
 ###### [Top](#top)
 
<br/>

***

<br/>

## 기타, 도움링크
- CS공부 하기 좋은 사이트 : https://gyoogle.dev/blog/computer-science/data-structure/Heap.html

###### [Top](#top)

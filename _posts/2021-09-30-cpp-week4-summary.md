---
title: C++ 4주차 요약
author: Gi-Chang Kim (Panther)
date: 2021-09-30 00:40 +0900
categories: [Inst, CPP]
tags: [cpp, inst, summary]
---

## 함수의 정의와 호출, 선언

### 함수 정의

함수의 이름과 매개변수, 리턴형, 이 함수가 수행할 기능을 정의한다.

```CPP
void display() {
    cout << "안녕";
}
```

### 함수 호출

정의한 함수를 사용하기 위해서 함수의 이름과 매개변수를 작성해 호출한다.

```CPP
int main() {
    display()
}
```

### 함수 선언

함수의 이름과 매개변수, 리턴형을 선언해 컴파일러에게 함수에 대한 정보를 미리 제공한다.

```CPP
void display();
```

## 살매개변수와 형식매개변수

### 실매개변수 (Actual Parameter: Argument)

```CPP
int main() {
    int sum;
    sum = add(5, 10);
}
```

add() 함수를 호출할 때 사용된 매개변수 5와 10처럼 어떤 함수를 호출할 때 사용되는 매개변수를 실매개변수라고 한다.

### 형식매개변수 (Formal Parameter: Parameter)

```CPP
int add(int x, int y) {
    return (x+y);
}
```

add() 함수 정의에 사용된 x와 y처럼 실매개변수를 전달받기 위해 사용되는 매개변수를 형식매개변수라고 한다.

## 매개변수 전달 방식

### 값에 의한 호출 (Call by Value)

실매개변수의 **값**을 형식매개변수로 전달하는 방식이다.
이 방식은 실매개변수를 형식매개변수로 전달하는 역할만 수행할 뿐, 함수 내부에서 형식매개변수가 변경되더라도 실매개변수는 변하지 않는다.

```CPP
#include <iostream>
using namespace std;
int sum(int x, int y);
int main() {
    int a = 2, b = 5, c = 0;
    cout << "sum() 호출 전 a: " << a << " b: " << b << " c: " << c << endl;
    c = sum(a, b);
    cout << "sum() 호출 후 a: " << a << " b: " << b << " c: " << c << endl;
    return 0;
}
int sum(int a, int b) {
    a = a + 2;
    b = b + 5;
    cout << "sum() 함수 내 a: " << a << " b: " << b << " a+b: " << a + b << endl;
    return (a+b);
}
```

### 주소에 의한 호출 (Call by Reference)

실매개변수의 **주소**를 형식매개변수로 전달하는 방식이다.
형식매개변수가 변할 때 실매개변수도 변하게 하기 위해서 포인터를 이용해 실매개변수의 주소를 전달한다.

```CPP
#include <iostream>
using namespace std;
int sum(int *px, int *py);
int main() {
    int a = 2, b = 5, c = 0;
    cout << "sum() 호출 전 a= "<< a <<" b= "<< b <<" c= "<< c << endl;
    c = sum(&a, &b);
    cout << "sum() 호출 후 a= "<< a <<" b= "<< b <<" c= "<< c << endl;
    
    return 0;
}
int sum(int *px, int *py) {
    *px = *px + 2;
    *py = *py + 5;
    return (*px+*py);
}
```

## 변수

### 지역 변수

지역 변수는 변수를 선언한 함수나 블록 내에서만 사용할 수 있다.

```CPP
int main() {
    int a = 5; // 지역 변수
    ...
}
```

### 전역 변수

함수 밖에서 변수를 선언하며 소스 전체에서 사용할 수 있다.

```CPP
int a = 5; // 전역 변수
int main() {
    ...
}
```

### 기억 클래스

#### 자동 (Auto)

가장 많이 사용되는 기억 클래스로, 기억 클래스가 명시되지 않은 변수는 모두 자동 변수로 선언된다.
스택 공간을 일시적으로 사용하며 함수나 블록에 진입하면 기억 영역이 확보되며 벗어나면 기억 영역은 바로 소거되지만 return 문으로 리턴된 값은 스택에 복사되어 외부로 전달된다.
초기화는 실행 시에 이루어지며 초기화 되지 않으면 임의의 값을 가지게 된다.

#### 정적 (Static)

프로그램이 종료될 때 까지 처음 선언한 변수의 값이 유지되며 처음 실행시 한 번만 초기화된다.
지역 Static 변수는 해당 블록내에서만 접근할 수 있으며 변수의 자료형 앞에 static을 쓰면 정적 변수로 선언된다.
전역 변수는 기본적으로 Static 변수로 선언된다.

## 구조체

이미 정의된 서로 다른 자료형들을 구성 요소로서 모아서 새로운 자료형을 만든다.
동일한 자료형만 관리할 수 있는 배열과는 달리 서로 다른 유형의 자료형들도 함께 관리할 수 있다.

구조체는 다음과 같이 선언한다:

```CPP
struct Man {
    char name[10];
    int age;
    double weight;
};
```

name, age, weight 변수를 멤버로 갖는 Man 자료형이 만들어졌다.

구조체 변수를 만드는 방법은 다음과 같다:

```C
struct Man Gildong;
```

```CPP
Man Gildong;
```

C와 C++에서의 구조체 변수 선언의 차이점은 C에서는 **struct 구조체명 변수명** 형식으로 선언하지만 C++에서는 struct를 생략하고 선언할 수 있다.

구조체 변수에서 멤버에 접근하는 방법은 다음과 같다:

```C
struct Man gildong;
struct Man *gangsu;
gildong.age = 15;
gangsu->age = 33;
```

일반 구조체 변수는 '.'을 이용해 멤버에 접근하고 포인터 구조체 변수는 '->'를 이용해 멤버에 접근한다.

## 출처

C++프로그래밍(21-2학기)한성현교수 강의 내용 변형 및 요약
---
title: C++ 9주차 요약
author: Ki-Chang Kim (Panther K)
date: 2021-11-02 21:27 +0900
categories: [College, CPP]
tags: [college, cpp]
---

## const 멤버

const형 멤버함수는 해당 멤버변수를 변경하는 연산을 수행할 수 없으며 const로 지정된 함수는 멤버변수의 값을 변경할 수 없으며 멤버를 참조만 하는 읽기 전용 함수가 된다.   
const 함수는 const 함수만 호출할 수 있으며 일반 멤버함수에는 접근할 수 없다.   
const 형을 선언할 때 멤버변수는 형 앞에, 멤버함수는 괄호 뒤에 const를 추가한다.

```cpp
const int age;
int getAge() const;
```

## const 객체

객체가 const로 지정되면 해당 객체에 초기화된 데이터는 변경할 수 없으며 const로 지정된 멤버함수만 호출할 수 있다.   
객체를 정의할 때 클래스 이름 앞에 const를 추가하여 객체를 const로 지정할 수 있다.

```CPP
const Dog happy;
```

## 동적 메모리 할당

지역 변수를 전역 변수처럼 프로그램이 끝날 때까지 값을 유지하고 싶거나 프로그램을 실행할 때 메모리의 양을 결정해야할 때 동적 메모리를 사용한다.   
실행시 필요한 메모리를 필요한 만큼만 할당하며 메모리의 주소를 사용하여 접근한다.   

C에서는 malloc() 함수를 이용해 동적 메모리를 할당하고 free() 함수로 해제한다.   
C++에서는 new 연산자를 이용해 동적 메모리를 할당하고 delete 연산자로 해제한다.

## 기타

C++프로그래밍(21-2학기)한성현교수 강의 내용 변형 및 요약
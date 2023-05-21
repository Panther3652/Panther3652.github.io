---
title: C++ 11주차 요약
author: Ki-Chang Kim (Panther K)
date: 2021-11-16 12:00 +0900
categories: [Inst, CPP]
tags: [cpp, inst, summary]
---

## 연산자 중첩

다형성을 구현하는 방법 중의 하나로, 기존에 사용되던 연산자의 기능을 클래스에서 새롭게 정의하여 사용한다. 연산자 중첩은 operator 키워드를 사용하며 단항연산자 중첩과 이항연산자 중첩이 있다.

## 단항연산자 중첩

피연산자가 하나일 때 사용되는 연산자 중첩으로 ++,--,-가 있으며 단항연산자를 중첩할 때는 매개변수가 필요하지 않다. 단항연산자 중첩은 전치 연산자와 후치 연산자 모두 사용할 수 있다.

## 이항연산자 중첩

연산자 양쪽에 피연산자가 필요한 +,-,*,/,% 등의 연산자 중첩으로 이항연산자 중첩은 한 개의 매개변수가 필요하다. 이는 연산자의 좌측 피연산자가 연산자 함수의 주체가 되고 우측의 피연산자만 있으면 되기 때문이다.

## 형변환 함수

한 객체의 자료형을 다른 객체의 자료형으로 변환시키고자 할 때 사용하며 리턴형에는 변환하고자 하는 자료형을, 변환값은 변환을 수행할 값을 넣는다. 형변환 함수는 매개변수를 가지지 않으며 형변환을 수행하는 클래스의 멤버함수이어야 한다.

## 과제

```CPP
#include <iostream>

class Point {
	int x, y;
public:
	Point() { x =0; y =0; }
	Point(int i, int j) { x = i; y = j; }
	Point operator -(Point ob);
	int getX() { return x; }
	int getY() { return y; }
};

Point Point::operator -(Point ob) {
	Point temp;
	temp.x = x - ob.x;
	temp.y = y - ob.y;
	return temp;
}

int main() {
	Point ob1(3, 5), ob2(4, 7), ob3;
	ob3 = ob1 - ob2;
	std::cout << ob3.getX() <<","<< ob3.getY();
    
	return 0;
}
```

## 기타

C++프로그래밍(21-2학기)한성현교수 강의 내용 변형 및 요약
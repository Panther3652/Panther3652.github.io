---
title: C++ 6주차 요약
author: Ki-Chang Kim (Panther K)
date: 2021-10-12 22:03 +0900
categories: [College, CPP]
tags: [college, cpp]
---

## 클래스 (Class)

### Integer 클래스와 객체

```cpp
class Integer {         // Integer라는 이름의 클래스
    private:            // 속성
        int val;        // 멤버 변수 / private 속성
    public:             // 속성
        int getVal();   // 멤버 함수 / 출력 / getter
        int setVal();   // 멤버 함수 / 입력 / setter
} Val1;                 // 객체 정의 방법 1
Integer Val2;           // 객체 정의 방법 2
```

### 멤버 함수 정의

#### 클래스 내부에서 정의

```cpp
class Dog {
    private:
        int age;
    public:
        int getAge() {
            return age;
        }
        void setAge(int a) {
            age = a;
        }
}
```

#### 클래스 외부에서 정의

```cpp
class Dog {
    private:
        int age;
    public:
        int getAge();
        void setAge(int age);
}

int Dog::getAge() {
    return age;
}

void Dog::setAge(int a) {
    age = a;
}
```

## Using, Namespace

### std Namespace

C++ 표준 라이브러리 네임스페이스, 대표적으로 cin, cout이 있다.

### Using 지시문 (Directive)

```cpp
using namespace std;
```

std 네임스페이스의 모든 것을 사용함을 알린다.   
컴파일러가 인식하지 못하는 이름을 찾으면 std 네임스페이스를 검사한다.

## Inline 함수

C에서의 #define 문을 이용한 매크로 함수와 유사하다.   
함수 선언, 정의 앞에 inline 키워드를 사용하여 매크로 함수의 부작용을 없애면서 같은 기능을 수행한다.   
inline 함수는 함수 코드 블록의 복사본인 기계어 코드가 직접 삽입된다.

## 과제

### Integer 클래스

![week6-summary-1](https://i.imgur.com/IT6mWaJ.png){: width="244" height="265"}

### Man 클래스

#### 멤버 함수 클래스 내부 정의

```cpp
#include <iostream>
using namespace std;

class Man {
    private:
        string name;
        int age;
        double weight;
    public:
        string getName() {
            return name;
        }
        void setName(string a) {
            name = a;
        }
        int getAge() {
            return age;
        }
        void setAge(int a) {
            age = a;
        }
        double getWeight() {
            return weight;
        }
        void setWeight(double a) {
            weight = a;
        }
};

int main() {
    Man kim;
    kim.setName("김기창");
    kim.setAge(20);
    kim.setWeight(57.4);
    cout << kim.getName() << "의 나이는 " << kim.getAge() << ", 몸무게는 " << kim.getWeight() << "입니다.";
    
    return 0;
}
```

#### 멤버 함수 클래스 외부 정의

```cpp
#include <iostream>
using namespace std;

class Man {
    private:
        string name;
        int age;
        double weight;
    public:
        string getName();
        void setName(string a);
        int getAge();
        void setAge(int a);
        double getWeight();
        void setWeight(double a);
};

string Man::getName() {
    return name;
}

void Man::setName(string a) {
    name = a;
}

int Man::getAge() {
    return age;
}

void Man::setAge(int a) {
    age = a;
}

double Man::getWeight() {
    return weight;
}

void Man::setWeight(double a) {
    weight = a;
}

int main() {
    Man kim;
    kim.setName("김기창");
    kim.setAge(20);
    kim.setWeight(57.4);
    cout << kim.getName() << "의 나이는 " << kim.getAge() << ", 몸무게는 " << kim.getWeight() << "입니다.";
    
    return 0;
}
```

## 기타

C++프로그래밍(21-2학기)한성현교수 강의 내용 변형 및 요약
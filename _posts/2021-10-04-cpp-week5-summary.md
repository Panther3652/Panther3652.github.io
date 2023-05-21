---
title: C++ 5주차 요약
author: Ki-Chang Kim (Panther K)
date: 2021-10-04 22:54 +0900
categories: [Inst, CPP]
tags: [cpp, inst, summary]
---

## 객체 지향 프로그래밍

구조적 프로그래밍 기법을 계승, 발전시킨 개념
**객체(Object)**를 이용해 ***자료***와 ***처리 동작***을 하나로 묶어 다룬다.

## 객체 (Object)

**자료**와 **연산(함수, Method)**을 하나로 묶어 만든 요소
자료를 표현하는 **변수**와 객체의 행동을 정의한 **함수**로 구성

### 인스턴스 (Instance)

어떤 클래스에서 생성되거나 한 클래스에 속하는 객체

## 클래스 (Class)

객체의 속성을 정의하는 수단
객체의 타입(Type), 기본 규격(Specification)

## 객체 지향 기술

### 추상 자료형 (Abstraction Data Type) / 캡슐화 (Encapsulation)

자료에 대한 연산을 외부와 단절하는 개념
캡슐화된 정보는 외부에서 직접 접근할 수 없으며 자료에 대한 수정과 참조는 객체 내에서만 이루어진다.

### 상속 (Inheritance)

기본 클래스에 정의된 자료, 연산과 같은 속성을 파생 클래스가 상속받아 사용할 수 있게 한다.
프로그램 재사용이 수월하여 개발 비용과 복잡도를 줄일 수 있다.

### 다형성 (Polymorphism)

유사한 기능을 하나의 이름으로 복잡도를 감소시킨다.
하나의 함수 이름, 연산자(함수 중첩, 연산자 중첩, **Overloading**)를 여러 목적으로 사용한다.

### Unified Modeling Language (UML)

다이어그램 그림을 그려 프로그램의 구조를 설계해보는 것

주요 다이어그램:
 - 클래스 다이어그램 (Class Diagram)
 - 객체 다이어그램 (Object Diagram)
 - 쓰임새 다이어그램 (Use-case Diagram)
 - 상태 다이어그램 (State Diagram)
 - 시퀀스 다이어그램 (Sequence Diagram)
 - 활동 다이어그램 (Activity Diagram)
 - 협력 다이어그램 (Collaboration Diagram)
 - 컴포넌트 다이어그램 (Component Diagram)
 - 배치 다이어그램 (Deployment Diagram)

## 클래스 멤버 접근 권한

멤버 변수, 멤버 함수를 선언하기 전 액세스 권한 속성을 지정

클래스 외부에서 멤버에 접근할 수 있는 권한:
1. 전용 (Private)
    - 해당 클래스 내부에서만 접근 가능
    - 속성을 지정하지 않을 경우 기본으로 지정 (생략 가능)

2. 범용 (Public)
    - 외부에서 제한 없이 접근 가능

3. 보호 (Protected)
    - Private 속성이나 파생 클래스에서 접근 가능

## 출처

C++프로그래밍(21-2학기)한성현교수 강의 내용 변형 및 요약
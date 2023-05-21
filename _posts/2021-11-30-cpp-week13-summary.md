---
title: C++ 13주차 요약
author: Ki-Chang Kim (Panther K)
date: 2021-11-30 21:13 +0900
categories: [Inst, CPP]
tags: [cpp, inst, summary]
---

## 중첩(Overloading) vs 중복(Overriding)
Overloading은 함수/연산자 중첩으로 구현, Overriding은 가상함수로 구현
Overloading은 정적 바인딩, Overriding은 동적 바인딩
Overloading은 수평적/병렬 구조, Overriding은 수직적/상속 구조
Overloading의 작용 시점은 컴파일시, Overriding의 작용 시점은 실행시

## 바인딩
변수와 함수에 대한 메모리 할당이나 함수 호출이 발생했을 때 실체로 처리해야 하는 명령어들이 결정되는 시점으로 정적 바인딩과 동적 바인딩이 있다.
정적 바인딩은 컴파일 시 변수의 위치와 함수가 실행할 명령이 결정되는 경우로, 대표적으로 정적(Static) 변수, 중첩(Overloading)이 있다.
동적 바인딩은 실제 실행할 때 결정되는 경우에 사용되는 경우로, 대표적으로 지역 변수와 중복(Overriding)이 있다.

## 정적(Static) 멤버변수
클래스의 멤버 변수 선언문에 static 키워드를 붙여 멤버변수로 선언하며 모든 객체들이 정보를 공유할 목적으로 사용하는 변수다. 따라서 여러 객체들이 공유해야 하는 정보는 정적 멤버변수로 선언한다.

## 가상함수(Virtual Function)
Overriding을 구현하는 방법으로, 동적 바인딩이며 기본 클래스의 멤버함수 앞에 virtual 키워드를 붙여 가상함수로 선언할 수 있다. 객체 지향 프로그래밍의 다형성을 구현하는 한 방법으로, 파생 클래스가 기본 클래스의 멤버함수를 상속 후 재정의할 수 있다.

## 순수가상함수(Pure Virtual Function)
함수의 정의가 이루어지지 않고 함수만 선언된 것으로, 파생클래스에서 반드시 재정의 해야 하며 순수가상함수를 갖는 클래스를 추상클래스라 하며 추상클래스는 객체를 생성할 수 없다.

## 기타
C++프로그래밍(21-2학기)한성현교수 강의 내용 변형 및 요약
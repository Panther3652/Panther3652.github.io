---
title: C++ 12주차 요약
author: Ki-Chang Kim (Panther K)
date: 2021-11-23 20:14 +0900
categories: [College, CPP]
tags: [college, cpp]
---

## 기본클래스, 파생클래스

기본클래스와 파생클래스의 관계는 is a 관계로 이루어져 있으며 파생클래스는 기본클래스의 속성을 사용할 수 있다. 이때 기본클래스를 부모, 파생클래스를 자식으로 칭하기도 한다.

## 상속 접근 제어

상속 접근 제어 속성은 private, protected, public으로 나누어져 있다.   
public 상속 접근인 경우에는 기본 클래스의 public, protected 멤버들은 파생 클래스의 public, protected 멤버가 되며 기본 클래스의 private 멤버는 private 속성으로 남으며 파생 클래스에서 접근할 수 없다.   
private 상속 접근은 기본 클래스의 모든 멤버가 파생 클래스의 private 멤버가 되며 기본 클래스의 public 멤버들은 클래스 외부에서 접근이 불가능하며 오직 파생 클래스의 멤버함수에 의해서만 접근이 가능하다.   
protected 상속 접근 제어는 거의 사용되지 않으며 기본 클래스에서 private 속성을 유지하면서 파생 클래스에서 접근하는 것이 가능하며 기본 클래스의 protected 멤버들이 파생 클래스 멤버에서 접근할 수 있다는 점을 제외하면 private 접근과 동일하다.

## 상속 생성자, 소멸자

기본 클래스와 파생 클래스 모두 생성자와 소멸자를 가질 수 있으며 이때 생성자는 기본 클래스를 시작으로 이후 파생된 순서에 따라서 실행된다. 소멸자는 생성자 순서 실행의 역순으로 실행된다.

## 계층적 다중 상속

파생 클래스가 여러 개의 기본 클래스를 상속받을 수 있으며 파생 클래스가 또 다른 파생 클래스의 기본 클래스로 사용되는 방법으로 다중 클래스 계층을 형성한다.   
MFC는 계층적 구조를 통해 클래스를 상속한다.

## 기타

C++프로그래밍(21-2학기)한성현교수 강의 내용 변형 및 요약
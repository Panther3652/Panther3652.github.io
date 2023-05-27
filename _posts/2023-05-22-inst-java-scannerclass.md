---
title: '[Java 기초] Scanner 클래스'
author: Ki-Chang Kim (Panther K)
date: 2023-05-22 15:00 +0900
categories: [Inst, Java]
tags: [inst, java]
---

## System.in

System.in은 키보드 장치를 직접 제어하고 키 입력을 받는 표준 입쳑 스트림 객체에다.   
Java 애플리케이션은 System.in을 통해 사용자로부터 키를 입력받을 수 있지만 System.in은 입력된 키를 단순 바이트 정보로 애플리케이션에 전달만 하며 애플리케이션에서 바이트 정보를 문자, 숫자로 변환해야하는 번거로움이 있으므로 입력된 키를 사용자가 원하는 타입으로 변환해주는 Scanner 클래스를 라용하는 것이 효과적이다.   

## Scanner 사용하기

Scanner 클래스를 사용하기 위해선 코드 맨 앞줄에 다음의 import 문을 입력한다.

```java
import java.util.Scanner;
```

Scanner 클래스는 Java에서 기본으로 제공하는 java.util 패키지에 포함되어있다.

## 키 입력받기

Scanner 클래스는 입력된 키 값을 **공백 문자**를 기준으로 분리하여 **토큰 단위**로 읽는다.

## Scanner 클래스 메소드

- next()
  - 타입: String
    - 다음 토큰을 문자열로 리턴한다.
- nextLine()
  - 타입: String
    - '\n'을 포함하는 한 라인을 읽고 '\n'을 버린 나머지 문자열을 리턴한다.
- nextByte()
  - 타입: byte
    - 다음 토큰을 byte 타입으로 리턴한다.
- nextShort()
  - 타입: short
    - 다음 토큰을 short 타입으로 리턴한다.
- nextInt()
  - 타입: int
    - 다음 토큰을 int 타입으로 리턴한다.
- nextLong()
  - 타입: long
    - 다음 토큰을 long 타입으로 리턴한다.
- nextFloat()
  - 타입: float
    - 다음 토큰을 float 타입으로 리턴한다.
- nextDouble()
  - 타입: double
    - 다음 토큰을 double 타입으로 리턴한다.
- nextBoolean()
  - 타입: boolean
    - 다음 토큰을 boolean 타입으로 리턴한다.

## Scanner 객체 종료

Scanner 객체를 종료하려면 다음을 사용한다:

```java
scanner.close()
```

Scanner 객체가 종료되면 System.in도 함께 종료되므로 더 이상 System.in을 사용해 키 입력을 받틀 수 없다.   
또한, 애플리케이션 내에 Scanner 객체를 여러 개 생성해도 모두 하나뿐인 System.in을 공유하므로 한 군데에서 Scanner 객체가 종료되면 System.in도 종료되어 다른 Scanner 객체에서 키 입력을 빋을 수 없으므로 Scanner 객체는 하나만 생성하고 애플리케이션 전체에서 공유하는 것이 좋다.


## 예제 코드

### 정보 입력 후 출력: 이름, 사는 곳, 나이, 체중, 독신 여부

```java
import java.util.Scanner;

public class ScannerEx {
    public static void main(String [] args) {
        System.out.println("이름, 도시, 나이, 체중, 독신 여부를 빈 칸으로 분리하여 입력하세요.");
        Scanner scanner = new Scanner(System.in);

        String name = scanner.next();
        System.out.println("이름: " + name);

        String city = scanner.next();
        System.out.println("도시: " + city);

        int age = scanner.nextInt();
        System.out.println("나이: " + age + "살");

        double weight = scanner.nextDouble();
        System.out.println("체중: " + weight + "kg");

        boolean isSingle = scanner.nextBoolean();
        System.out.println("독신 여부: " + isSingle);

        scanner.close();
    }
}
```

### 2개의 정수를 입력받아 합을 출력

```java
import java.util.Scanner;

public class ScannerSum {
    public static int sum(int n, int m) {
        return n + m;
    }

    public static void main(String[] args) {
        System.out.println("정수 두 개를 입력하세요");
        Scanner scanner = new Scanner(System.in);

        int s;
        int i = scanner.nextInt();
        int j = scanner.nextInt();

        s = sum(i, j);

        System.out.println(s);
    }
}
```
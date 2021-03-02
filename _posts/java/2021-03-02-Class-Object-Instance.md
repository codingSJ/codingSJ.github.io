---
title: "JAVA_클래스, 객체, 인스턴스"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories:
- JAVA
description: 클래스와 객체, 그리고 인스턴스의 차이에 대해 알아보자.
toc: true
toc_sticky: true
toc_label: 목차
---

# 0. 이 글의 목적

- 클래스와 객체, 인스턴스의 정의와 그 차이를 알아본다.





# 1. 용어 정리

> 1-1. 정의

[Java 튜토리얼](https://www.tutorialspoint.com/java/java_object_classes.htm) 에 의하면 클래스와 객체에 대해 다음과 같이 설명한다.

- **Object(객체)** − Objects have states and behaviors.
  Example: A dog has states - color, name, breed as well as
  behaviors – wagging the tail, barking, eating. An object is an instance of a class.
- **Class(클래스)** − A class can be defined as a template/blueprint that describes the behavior/state that the object of its type support.



즉 객체란 어떤 속성과 동작을 갖고 있는 것으로 클래스의 인스턴스이다. 또 클래스란 어떤 객체의 속성과 동작을 정의하는 설계도 기능을 하는 것이다. 이제 객체와 클래스를 조금 더 깊게 알아보자.



> 1-2. 객체

**객체란 물리적으로 존재하거나 추상적으로 생각할 수 있는 것 중에서 자신의 속성과 독장을 가지며 다른 것과 구분 가능한 것을 말한다.** 예로 우리 눈에 보이는 사람, 차, 아파트 등 실제로 존재하는 것 외에도 강의, 주문 등 개념적인 것들도 객체라 할 수 있다. 또한 객체는 속성과 동작으로 구분된다. 속성(state)은 객체의 특징을 말하며 필드(field)라 불린다. 동작(behavior)은 객체가 수행하는 기능을 말하며 메소드(method)라 부른다.



객체 모델링(Object Modeling)이란 현실 세계의 객체를 소프트웨어 객체로 설정하는 것을 말한다. 즉 객체 모델링이란 현실 세계 객체를 속성과 동작으로 구분한 다음, 속성은 필드로, 동작은 메소드로 정의하는 과정이라 할 수 있다.



> 1-3. 클래스 & 인스턴스

위에서 언급한 어떤 객체를 사용하고 싶다면, 그 객체에 대한 세부 내용과 설명, 즉 설계도에 해당하는 것이 필요할 것이다. 이렇게 **객체의 설명서 기능을 하는 것이 클래스이다.** 객체는 속성(=필드)과 동작(=메소드)으로 구분된다고 설명했는데, 클래스에는 객체의 필드와 메소드를 정의가 필요하다. 그리고 이런 클래스에 의해 생성된 객체를 해당 클래스의 인스턴스라고 한다.



> 1-4. 용어 정리

클래스, 객체, 그리고 인스턴스에 대해 정리해보면 다음과 같다.



"클래스는 어떤 객체를 생성하기 위해 필요한 필드와 메소드를 정의해둔 설계도이다. 그리고 이 클래스에 의해 생성된 클래스의 인스턴스를 객체라고 한다. 이렇게 생성된 객체는 실존하는 것이거나 추상적으로 생각할 수 있는 것으로 다른 것과 구분 가능하다."



```java
int age;
double length = 10.15;
char alphabetA = 'A';
```

| 변수 타입 | 변수 이름 | 변수 값 |
| --------- | --------- | ------- |
| int       | age;      |         |
| double    | length    | 10.15   |
| char      | alphabetA | 'A'     |

정수 값을 저장할 수 있는 변수 age, 실수 값을 저장할 수 있고 10.15의 값으로 초기화한 변수 length, 문자를 저장할 수 있고 'A'의 값을 저장한 변수 alphabetA를 선언했음을 볼 수 있다. 또 age에서 볼 수 있듯이 항상 값을 동시에 선언해줄 필요는 없다.

위의 예시를 보면 A를 만들기 위해서는 우선 B가 있어야 한다. 즉 가장 작은 부품인 B를 만들고, B를 사용하는 A를 만든다. 하지만 다음 방법은 어떨까?



스프링의 DI는 큰 객체부터 시작되는 것이 아니라 작은 객체부터 시작된다. 즉 작은 객체부터 큰 객체로 이어지는, 역순(=Inversion of Control)으로 의존성을 주입한다.

따라서, IoC 컨테이너는 의존성을 갖고 있는 객체들을 모아둔 컨테이너인데, 가장 작은 객체부터 의존성 주입을 시작하는 컨테이너를 말한다.
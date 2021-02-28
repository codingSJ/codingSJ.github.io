---
title: DI( Dependecy Injection: 의존성 주입 )이란
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories:
- SPRING
toc: true
toc_sticky: true
toc_label: 목차
---

# 0. 이 글의 목적

- 스프링의 코어 개념 중 하나인 DI이 무엇인지 이해한다.
- DI의 2가지 방법을 알아본다.





# 1. DI의 개념

> 1-1. 두 객체 간의 연관관계

객체지향 언어를 이용해 개발을 하다보면, 하나의 객체를 표현하기 위해 다른 객체가 필요한 상황이 많다. 예를 들면 클래스 A를 정의하는데 있어 또 다른 클래스 B가 필요하다고 할 때, 우리는 A가 B를 사용하는 것을 다음과 같이 표현할 수 있다.



```java
//1방법
class A
{
    private B b;

    public A(){
        b = new B();
    }
}
```

```java
//2방법
class A
{
    private B b;

    public void setB(B b){
      this.b = b;
    }
}
```

- 1방법
  클래스 A의 객체를 생성할 때 B에 대한 언급을 안해줘도 스스로 B의 객체를 생성해 사용하는 방법. A를 만들면 자동으로 B가 따라오는 일체형 방식.
- 2방법
  클래스 A의 객체를 생성할 때 **외부에서** B의 객체를 넣어 A 객체를 조립해주는 방법. 즉 A를 사용하기 위해서는 B를 우선 선언해줘야하는 조립형 방식.

컴퓨터 본체 주문을 예시로 들어보자. 컴퓨터를 주문할 때 일체형 본체를 주문하면 업체에서 본체 케이스 안에 여러 부품들을 조립해서 갖다준다. 제품을 주문한 나는 본체 안에 어떤 부품들이 있는지 자세히 모르더라도 컴퓨터를 사용할 수 있다. 그에 비해 컴퓨터 본체 케이스부터 시작해 그래픽 카드, RAM, 메인보드, 하드 등 하나하나 주문해 조립하는 경우도 있다. 조립형의 경우 컴퓨터 본체를 구성하는 부품에 어떤 것들이 있는지 알고 있어야 가능한 경우다. 부품을 하나라도 안사면 내가 원하고자 했던 본체를 사용하지 못하는 경우다. 일체형 본체를 주문하는게 1방법, 조립형 본체를 주문하는게 2방법이다.



> 1-2. DI(Dependency Injection)

클래스 A의 객체를 선언할 때 위의 1방법과 2방법이 어떻게 사용되는지 보자.

```java
//1방법
A a = new A();
```

```java
//2방법
B b = new B();
A a = new A();

a.setB(b);
```

A의 객체를 선언할 때 1방법에서는 B의 존재에 대해 몰라도 된다. 하지만 2방법에서는 B의 존재를 반드시 알아야한다. 위의 컴퓨터 본체 주문을 되짚어봤을 때, A는 컴퓨터 본체 케이스, B는 그래픽 카드라 예를 들 수 있다. A에게 B는 하나의 부품이고, A를 생성하기 위해서는 B를 먼저 생성해줘야 하고 A를 만들 때 넣어줘야 한다.

이렇게 하나의 객체 B를 부품으로 사용하는 또 다른 객체 A에 조립해주는 것을 DI(Dependency Injection), 의존성 주입이라 한다. A를 만들기 위해 부품 B(Dependency)를 만들고 A를 생성할 때 넣어줘야(Injection) 한다. 그리고 이런 DI, 즉 의존성 주입에는 2가지 방법이 있다.



> 1-3. DI의 2가지 방법

DI에는 2가지 방법이 존재한다. Setter Injection과 Construction Injection. 그 차이를 알아보자.

```java
//Setter Injection
B b = new B();
A a = new A();

a.setB(b);
```

```java
//Construction Injection
B b = new B();
A a = new A(b);
```

Setter Injection은 생성 후에 Setter method를 통해 주입해주는 것이고 Construction Injection은 생성하는 동시에 주입하는 것이다.



> 1-3. DI를 대신 해주는 스프링

프로젝트가 복잡해질수록 DI 또한 많아질 것이고, 그러면 개발자 입장에서는 부담스러울 것이다. 스프링은 이런 부분을 대신 짊어진다. 스프링은 어떤 부품을 어디에 조립할 것인지만 스프링에게 알려준다면 스프링이 DI를 대신해주고 우리는 그 결과물만 사용할 수 있도록 도와준다. 이것이 스프링의 코어 개념 중 하나인 DI이다.
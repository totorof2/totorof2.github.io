---
layout: post
title:  "Structural Patterns"
date:   2018-03-20 16:03:33
permalink: /first-post.html
---

# Ch4 - Structural Patterns

## Proxy Pattern
* 실제 객체를 대신하는 프록시 객체를 사용해서 실제 객체의 생성이나 접근 등을 제어할수 있도록 해주는 패턴.
 * remote proxy, virtual proxy, protection proxy
* application needs와 database needs를 구분.
* Objectives
  * Hide an object behind the proxy so the features can be hidden, restricted, and so on
  * Provide a new abstraction layer that is easy to work with, and can be changed easily
* The [proxy pattern](https://en.wikipedia.org/wiki/Proxy_pattern) provides an object that controls access to another object, intercepting all calls.


## Decorator design pattern
* 위임을 하는 방식으로 기능을 확장해 나가는 패턴. (마트료시카 인형처럼)
* 기존 코드를 건드리지 않고 기능을 확장하고 싶을 때 적합(open/close principla)
* 정의되어있는 메서드가 증가하면 데코레이터 구현이 복잡해진다.

### Proxy vs Decorator
* 데코레이터 패턴에서는 동적으로 타입을 decorate한다. 즉 decoration이 있거나 없을수도 있음을 의미.
* 데코레이터에 의해 구현되지 않은 메소드의 호출은 데코레이팅된 타입으로 전달됨. 즉 데코레이팅할 타입이 구현하는 모든 인터페이스의 메소드를 데코레이터에서 구현하지 않아도 됨.
* 데코레이터 패턴은 런타임에 오류가 발생할 수 있어 프록시 패턴에 비해 더 취약하다.
  * Decorator는 웹서버와 같이 런타임에 객체에 기능을 추가할때 일반적으로 사용됨.
* 프록시 타입은 컴파일 타임에 오류를 잡을 수 있다.

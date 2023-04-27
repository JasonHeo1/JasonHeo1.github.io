---
layout: post
title: instanceof, isInstance, isAssignableFrom 차이점
categories: [Java]
description: instanceof, isInstance, isAssignableFrom
keywords: Java, instanceof, isInstance, isAssignableFrom
mermaid: false
sequence: false
flow: false
mathjax: false
mindmap: false
mindmap2: false
---


Java에서 클래스와 객체의 타입 체크와 관련된 개념으로 `instanceof`, `Class.isInstance()`, `Class.isAssignableFrom()`이 있습니다.

1. instanceof

`instanceof` 연산자는 객체가 특정 클래스의 인스턴스인지를 확인하는 데 사용됩니다. 결과 값은 boolean 타입으로, 객체가 특정 클래스의 인스턴스이면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.

예를 들어, 아래 코드는 `myObject`가 `MyClass`의 인스턴스인지를 확인하는 코드입니다.

```java
MyClass myObject = new MyClass();
if (myObject instanceof MyClass) {
    System.out.println("myObject is an instance of MyClass");
}
```

위 코드에서 `myObject instanceof MyClass`는 `myObject`가 `MyClass`의 인스턴스인지를 확인하는 코드입니다. `true`가 반환되므로, "myObject is an instance of MyClass"이 출력됩니다.

2. Class.isInstance()

`Class.isInstance()` 메소드는 객체가 특정 클래스의 인스턴스인지를 확인하는 데 사용됩니다. `instanceof`와 유사하게 동작하지만, `isInstance()` 메소드는 객체를 직접 전달받아 타입 체크를 수행합니다.

예를 들어, 아래 코드는 `myObject`가 `MyClass`의 인스턴스인지를 확인하는 코드입니다.

```java
MyClass myObject = new MyClass();
Class<?> clazz = MyClass.class;
if (clazz.isInstance(myObject)) {
    System.out.println("myObject is an instance of MyClass");
}
```

위 코드에서 `clazz.isInstance(myObject)`는 `myObject`가 `MyClass`의 인스턴스인지를 확인하는 코드입니다. `true`가 반환되므로, "myObject is an instance of MyClass"이 출력됩니다.

3. Class.isAssignableFrom()

`Class.isAssignableFrom()` 메소드는 두 개의 클래스 타입을 비교하여, 첫 번째 클래스가 두 번째 클래스의 하위 클래스인지를 확인하는 데 사용됩니다. 결과 값은 boolean 타입으로, 첫 번째 클래스가 두 번째 클래스의 하위 클래스이면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.

```java
System.out.println(ArrayList.class.isAssignableFrom(Object.class)); //false
System.out.println(Object.class.isAssignableFrom(ArrayList.class)); //true
```

위 코드에서 `class2.isAssignableFrom(class1)`은 `MyClass` 클래스가 `Object` 클래스의 하위 클래스인지를 확인하는 코드입니다. `true`가 반환되므로, "MyClass is a subclass of Object"이 출력됩니다.
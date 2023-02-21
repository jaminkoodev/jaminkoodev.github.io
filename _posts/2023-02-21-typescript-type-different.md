---
title:  "[TypeScript] type과 Type의 차이"
excerpt: "TypeScript의 type과 Type의 차이에 대해 알아보자"

categories:
  - TypeScript
tags:
  - [TypeScript]

toc: true
toc_sticky: true
 
date: 2023-02-21
last_modified_at: 2023-02-21
---
## Type과 type의 차이?
TypeScript에서 `type`과 `Type`은 모두 타입을 정의하는 키워드이지만, 사용 방법이 약간 다릅니다.

`type`은 타입 별칭(Type Alias)을 정의하는 키워드입니다. 이는 타입을 다른 이름으로 선언하여 재사용 가능하도록 만드는 기능으로, 불필요한 중복을 줄일 수 있습니다.

```typescript
type MyNumber = number;
type MyString = string;

let myNum: MyNumber = 10;
let myString: MyString = 'Hello, World!';
```

반면, `Type`은 클래스 또는 인터페이스 등을 상속받는 새로운 타입을 정의하는 키워드입니다. 이는 객체지향 프로그래밍에서 다형성을 구현할 때 유용합니다.

```typescript
interface Shape {
  draw(): void;
}

class Circle implements Shape {
  draw() {
    console.log('Circle.draw()');
  }
}

type Square = { draw(): void } & Shape;

class MySquare implements Square {
  draw() {
    console.log('MySquare.draw()');
  }
}
```
즉, `type`은 타입을 별칭으로 사용할 때, `Type`은 상속을 통해 새로운 타입을 정의할 때 사용됩니다.
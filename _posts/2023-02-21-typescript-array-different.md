---
title:  "[TypeScript] type[]과 `array<type>`의 차이"
excerpt: "TypeScript의 type[]과 `array<type>`의 차이에 대해 알아보자"

categories:
  - TypeScript
tags:
  - [TypeScript]

toc: true
toc_sticky: true
 
date: 2023-02-21
last_modified_at: 2023-02-21
---

## type[] 과 array[type] ?

`type[]`은 배열을 나타내는 타입으로, 해당 배열의 요소가 type이어야 함을 명시합니다. 예를 들어 `string[]`은 문자열로 이루어진 배열을 나타내는 타입입니다.

`Array<type>`은 제네릭 타입을 사용하여 배열을 나타내며, `<type>` 자리에 해당 배열의 요소 타입을 지정합니다. 이 방법은 배열을 나타내는 타입이 복잡한 경우 유용할 수 있습니다. 예를 들어, `Array<string | null>`은 문자열 또는 `null` 값을 가질 수 있는 배열을 나타내는 타입입니다.

타입스크립트에서 `type[]`과 `Array<type>`은 기능적으로 동일하며, 배열을 나타내는 데 사용할 수 있습니다. 

다만 `type[]` 방식이 간단하고 익숙한 문법을 사용하므로 일반적으로 더 선호되는 방식입니다.

```typescript
// string[] 타입 사용
const strArr: string[] = ['apple', 'banana', 'cherry'];

// Array<string> 타입 사용
const arrStr: Array<string> = ['apple', 'banana', 'cherry'];

// number[] 타입 사용
const numArr: number[] = [1, 2, 3];

// Array<number> 타입 사용
const arrNum: Array<number> = [1, 2, 3];
```
위 예제에서는 `string[]`와 `Array<string>`이 서로 같은 의미를 가지고 있습니다. 

마찬가지로 `number[]`와 `Array<number>`도 같은 의미를 가지고 있습니다. 

`string[]`와 `Array<string>`의 차이점이 있다면, 타입스크립트에서는 `string[]`을 더 자주 사용한다는 점이 있습니다. 하지만 이는 개인적인 스타일에 따라 다르기도 합니다.
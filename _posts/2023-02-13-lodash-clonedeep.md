---
title:  "[Javascript] lodash의 cloneDeep과 cloneDeepWith 의 차이"
excerpt: "lodash의 cloneDeep과 cloneDeepWith 의 차이를 알아보자"

categories:
  - javascript
tags:
  - [javascirpt, typescript, lodash]

toc: true
toc_sticky: true
 
date: 2023-02-13
last_modified_at: 2023-02-13
---

# lodash의 `cloneDeep` 과 `cloneDeepWith`의 차이
lodash 라이브러리에서는 객체의 복사를 위해 `cloneDeep`과 `cloneDeepWith` 두 가지 메서드를 제공합니다.

## cloneDeep
`cloneDeep` 메서드는 주어진 객체의 깊은 복사본을 반환합니다. 깊은 복사는 객체 내의 모든 값이 새로운 값으로 복사되어, 원래 객체와 별개의 객체가 생성되는 것을 의미합니다.

예를 들어, 다음 코드에서 originalObject와 clone은 서로 다른 객체입니다

```javascript
const originalObject = { a: 1, b: { c: 2 } };
const clone = _.cloneDeep(originalObject);

clone.a = 2;
console.log(originalObject.a); // 1
```

## cloneDeepWith
`cloneDeepWith` 메서드는 주어진 객체의 깊은 복사본을 반환하지만, 특정 값의 복사 로직을 사용자 정의 함수를 통해 지정할 수 있습니다.

예를 들어, 다음 코드에서 originalArray와 clone은 서로 다른 배열입니다. 그러나 clone 배열의 첫 번째 값은 originalArray의 첫 번째 값과 같은 객체입니다:

```javascript
const originalArray = [{ a:
```
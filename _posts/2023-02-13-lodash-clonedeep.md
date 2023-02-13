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
`lodash`는 프로그래밍 작업에 필요한 일반적인 유틸리티 기능을 제공하는 JavaScript 라이브러리입니다. 

`cloneDeep`과 `cloneDeepWith`는 두 개의 `lodash` 라이브러리 함수로, 객체와 배열의 깊은 복사를 만드는 데 사용됩니다.

## cloneDeep
`cloneDeep`은 객체 또는 배열의 모든 속성과 요소를 재귀적으로 새 객체 또는 배열로 복사하여 객체 또는 배열의 깊은 복사본을 만드는 데 사용됩니다. 

이 함수는 숫자, 문자열, 불리언과 같은 기본 데이터 유형의 속성 및 요소는 얕은 복사만 할 것입니다. 하지만 원본 객체 또는 배열에 포함된 객체 또는 배열은 깊은 복사가 됩니다.

```javascript
const _ = require('lodash');

const original = {
  a: 1,
  b: {
    c: 2
  },
  d: [3, 4, 5]
};

const copied = _.cloneDeep(original);

console.log(copied);
// 출력: { a: 1, b: { c: 2 }, d: [ 3, 4, 5 ] }
```

## cloneDeepWith
`cloneDeepWith`은 `cloneDeep`과 비슷하지만 특정 속성 및 요소를 복제하는 데 필요한 고객 정의 함수를 제공하는 것을 허용합니다. 

이는 특정 속성이나 요소를 적절하게 복제하는 데 필요한 사용자 정의 논리가 있는 경우에 유용할 수 있습니다.

```javascript
const _ = require('lodash');

const original = {
  a: 1,
  b: {
    c: 2
  },
  d: [3, 4, 5]
};

const customizer = (value) => {
  if (_.isNumber(value)) {
    return value * 2;
  }
};

const copied = _.cloneDeepWith(original, customizer);

console.log(copied);
// 출력: { a: 2, b: { c: 4 }, d: [ 6, 8, 10 ] }
```
이 예제에서는 `cloneDeepWith` 함수에 `customizer` 함수가 제공되어, 원본 객체에 포함된 각 숫자의 값을 두 배로 복사합니다. 결과적으로 복사된 객체의 모든 숫자 값은 2배가 됩니다.
---
title:  "[Vue] vue의 created과 mounted 의 차이"
excerpt: "vue의 created과 mounted 의 차이를 알아보자"

categories:
  - vue
tags:
  - [vue, javascirpt, typescript]

toc: true
toc_sticky: true
 
date: 2023-02-13
last_modified_at: 2023-02-13
---

# vue의 `created` 과 `mounted` 의 차이

`Vue.js`에서 `created`와 `mounted`는 컴포넌트의 라이프사이클의 특정 시점에서 코드를 실행할 수 있는 라이프사이클 훅입니다.

## created
인스턴스가 생성되고 모든 데이터와 메소드가 초기화된 후 호출되는 라이프사이클 훅입니다. 

이것은 첫 번째로 호출되는 라이프사이클 훅이며 API에서 데이터를 가져오는 등의 설정 작업을 수행하는 곳입니다. 

그러나 이 단계에서는 컴포넌트가 아직 DOM에 추가되지 않았기 때문에 DOM 조작은 아직 적용되지 않습니다.

## mounted
라이프사이클 훅은 컴포넌트가 DOM에 추가되어 완전히 가시적이고 대화적이 된 후 호출됩니다. 

이 단계에서, 컴포넌트의 데이터와 템플릿이 업데이트되고 모든 반응형 데이터 변경 사항이 적용됩니다. 

이것이 DOM 조작을 수행하는 가장 좋은 장소입니다 (예 : 이벤트 리스너 설정) 컴포넌트가 이제 사용자와 상호 작용할 준비가 되었기 때문입니다.


아래는 `created` 와 `mounted `라이프사이클 훅의 차이를 보여주는 예제입니다.

```html
<template>
  <div>
    <p>{{ message }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: ''
    };
  },
  created() {
    console.log('created hook');
    this.message = 'created hook';
  },
  mounted() {
    console.log('mounted hook');
    this.message = 'mounted hook';
  }
};
</script>
```

이 예제에서는 메시지를 표시하는 간단한 Vue 컴포넌트가 있습니다. 메시지는 data 메소드에서 빈 문자열로 초기화됩니다.

created 훅에서는 콘솔에 메시지를 기록하고 메시지를 "created hook" 으로 설정합니다.

mounted 훅에서는 또 다른 메시지를 콘솔에 기록하고 메시지를 "mounted hook" 으로 설정합니다.

이 컴포넌트를 실행하면 콘솔에 다음과 같은 출력을 볼 수 있습니다.
```
created hook
mounted hook
```

`created hook`과 `mounted hook`의 차이점을 보여줍니다. 

`created hook`은 컴포넌트가 생성되고 데이터가 초기화되자마자 호출됩니다. 반면, `mounted hook`은 컴포넌트가 DOM에 마운트되고 사용자와 상호작용이 가능한 상태가 되자마자 호출됩니다.

이 예제에서는 created hook에서는 메시지를 "created hook"로 설정하지만, mounted hook에서 다시 "mounted hook"로 설정되어 화면에 표시됩니다.


## 정리
요약하면, `created`와 `mounted`의 차이점은 `created`가 컴포넌트가 생성된 후지만 DOM에 추가되기 전에 호출되는 반면, `mounted`는 컴포넌트가 DOM에 추가되어 완전히 가시적(visible)이고 상호작용적(interactive)이 된 후 호출됩니다.


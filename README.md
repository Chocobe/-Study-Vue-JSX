##### top
# Vue JSX 스터디

* [01. 개요](#01)

* [02. JSX 환경설정 - babel](#02)



<br/><hr/><br/>



##### 01
## 01. 개요

Vue 컴포넌트를 작성할 때 일반적인 방법은 다음과 같습니다.

```html
<!-- 경로: "@/components/MyComponent.vue"> -->

<template>
  <div>
    <h1 class="my-title">{{ msg }}</h1>
  </div>  
</template>

<script>
export default {
  data: () => ({
    msg: "My Component 입니다.",
  }),
};
</script>

<style scoped>
.my-component {
  color: #ff1493;
}
</style>
```

<br/>

<img src="./readmeAssets/01-개요-01.png" width="700px"><br/>

<br/>

위의 코드에서 ``<template>``을 생략하고, render(h) 메서드로 구현하면 다음과 같습니다.

```html
<!-- 경로: "@/components/MyRender.vue" -->

<script>
export default {
  data: () => ({
    msg: "My Render 입니다.",
  }),

  render(h) {
    return h("h1", {
      class: ["my-render-title"],
      
      domProps: {
        innerHTML: this.msg,
      },
    });
  },
};
</script>

<style scoped>
.my-render-title {
  color: #03a9f4;
}  
</style>
```

<br/>

<img src="./readmeAssets/01-개요-02.png" width="700px"><br/>

<br/>

render(h) 를 사용해도 동일한 결과가 나옵니다.

만약, MyRender.vue 의 하위 요소가 3개 라면 다음과 같이 작성하게 됩니다.

```html
<!-- 경로: "@/components/MyComplexJsx.vue" -->
<script>
export default {
  data: () => ({
    title: "My Complex Render 입니다.",
    contents: "컨텐츠 입니다.",
    buttonName: "버튼명",
  }),

  render(h) {
    return h("div", [
      h("h1", {
        class: ["my-complex-title"],
        domProps: {
          innerHTML: this.title,
        },
      }),

      h("p", {
        class: ["my-complex-contents"],
        domProps: {
          innerHTML: this.contents,
        },
      }),

      h("button", {
        class: ["my-complex-button"],
        domProps: {
          innerHTML: this.buttonName,
        },
      }),
    ]);
  },
};
</script>

<style scoped>
.my-complex-title {
  color: #ff1493;
}

.my-complex-contents {
  color: #34eb7a;
}

.my-complex-button {
  color: #2b51b9;
  font-weight: 900;
}
</style>
```

<img src="./readmeAssets/01-개요-03.png" width="700px"><br/>

<br/>

위의 MyComplexRender 컴포넌트에서 하위 요소를 출력하기 위해 작성한 render(h) 메서드를 보면, 상당히 복잡해 보입니다.

```javascript
render(h) {
  return h("div", [
    h("h1", {
      class: ["my-complex-title"],
      domProps: {
        innerHTML: this.title,
      },
    }),

    h("p", {
      class: ["my-complex-contents"],
      domProps: {
        innerHTML: this.contents,
      },
    }),

    h("button", {
      class: ["my-complex-button"],
      domProps: {
        innerHTML: this.buttonName,
      },
    }),
  ]);
};
```

<br/>

여기서 사용한 ``h()`` callback 함수는 ``createElement()`` 함수로, DOM 요소를 VNode 로 만들어주는 callback 함수 입니다.

Javascript 함수 문법에 맞는 입력을 하다보니, 위와같이 복잡한 코드를 작성하게 되는데, 이 문제를 해결할 수 있는 방법이 ``JSX`` 입니다.



<br/>

[🔺 Top](#top)

<hr/><br/>



##### 02

<template>
  <div id="app">
    <!-- <my-component /> -->
    <!-- <my-render /> -->
    <!-- <my-complex-render /> -->
    <!-- <my-jsx /> -->
    <my-complex-jsx />
  </div>
</template>

<script>
// import MyComponent from "@/components/MyComponent.vue";
// import MyRender from "@/components/MyRender.vue";
// import MyComplexRender from "@/components/MyComplexRender.vue";
// import MyJsx from "@/components/MyJsx.vue";
import MyComplexJsx from "@/components/MyComplexJsx.vue";

export default {
  components: {
    // MyComponent,
    // MyRender,
    // MyComplexRender,
    // MyJsx,
    MyComplexJsx,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>

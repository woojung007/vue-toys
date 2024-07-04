<template>
  <!-- <InputExample /> -->
  <!-- <VueDongsan /> -->
  <TodoApp />
</template>

<script>
import InputExample from "./components/InputExample.vue";
import VueDongsan from "./components/VueDongsan.vue";
import TodoApp from "./components/data-binding/TodoApp.vue";

export default {
  name: "App",

  components: {
    InputExample,
    VueDongsan,
    TodoApp,
  },
};
</script>

<style>
body {
  margin: 0;
}

div {
  box-sizing: border-box;
}
</style>

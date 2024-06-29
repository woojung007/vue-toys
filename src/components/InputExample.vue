<template>
  <div>
    <h2>Input Value</h2>
    <!-- <input
      type="text"
      :value="inputValue"
      @input="(event) => (inputValue = event.target.value)"
    /> -->
    <input type="text" v-model="inputValue" />
    <div class="example_value">
      {{ inputValue }}
    </div>

    <textarea type="text" v-model.lazy="textareaValue" />
    <div class="example_value">
      {{ textareaValue }}
    </div>
  </div>
</template>

<script lang="ts">
import { ref } from "vue";

export default {
  setup() {
    const inputValue = ref(null);
    const textareaValue = ref(null);
    return { inputValue, textareaValue };
  },
};
</script>

<style>
.example_value {
  height: 50px;
}
</style>

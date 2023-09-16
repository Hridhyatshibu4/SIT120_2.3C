<template>
  <div>
    <!-- Step 1a: Text Interpolation -->
    <p>Step 1a: Text Interpolation</p>
    <p>{{ message }}</p>

    <!-- Step 1b: Raw HTML [v-html] -->
    <p>Step 1b: Raw HTML [v-html]</p>
    <p v-html="htmlContent"></p>

    <!-- Step 1c: Attribute Bindings [v-bind:id] -->
    <p>Step 1c: Attribute Bindings [v-bind:id]</p>
    <input :id="inputId" />

    <!-- Step 1d: JavaScript expressions inside syntax i.e.{{ }} -->
    <p>Step 1d: JavaScript expressions inside syntax i.e.{{ }}</p>
    <p>{{ 2 + 2 }}</p>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    // Step 3: Reactivity Fundamentals [ref()]
    const message = ref("Hello, Vue 3!");

    return {
      message,
      htmlContent: '<strong>Rendered with v-html</strong>',
      inputId: 'my-input',
    };
  },
};
</script>

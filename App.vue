<template>
  <div>
    <!-- Step 1: Template Syntax -->
    <HelloWorld /> <!-- Render the HelloWorld component -->

    <!-- Step 5: Class and Style Bindings -->
    <!-- Conditional class binding: 'active' class is applied if 'isActive' is true -->
    <div :class="{ active: isActive }">Conditional class binding</div>

    <!-- Step 6: List Rendering -->
    <ul>
      <!-- Step 6a: v-for with an Object -->
      <!-- Iterate through 'items' object, displaying key and value -->
      <li v-for="(value, key) in items" :key="key">{{ key }}: {{ value }}</li>

      <!-- Step 6b: v-for with a Range -->
      <!-- Iterate through a range from 1 to 3 -->
      <li v-for="n in 3" :key="n">Range: {{ n }}</li>

      <!-- Step 6c: v-for on <template> -->
      <!-- Iterate through 'items' array, rendering each 'item' -->
      <template v-for="item in items" :key="item">
        <li>{{ item }}</li>
      </template>
    </ul>

    <!-- Step 7: Event Handling -->
    <!-- Button with click event handler 'handleClick' -->
    <button @click="handleClick">Click me</button>

    <!-- Step 8: Form Input Bindings -->
    <!-- Input field bound to 'inputValue' using v-model -->
    <input type="text" v-model="inputValue" />

    <!-- Step 11: Components -->
    <!-- Render 'ItemComponent' with prop 'item' set to 5 -->
    <ItemComponent :item="5" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import ItemComponent from "./components/ItemComponent.vue";
import { ref } from 'vue';

export default {
  components: {
    HelloWorld,
    ItemComponent,
  },
  setup() {
    // Step 5: Class and Style Bindings
    const isActive = ref(true);

    // Step 6: List Rendering
    const items = ref([1, 2, 3]);

    // Step 7: Event Handling
    const handleClick = () => {
      console.log("Button clicked!");
    };

    // Step 8: Form Input Bindings
    const inputValue = ref("");

    return {
      isActive, // Make 'isActive' reactive
      items, // Make 'items' reactive
      handleClick, // Event handler
      inputValue, // Bind input value
    };
  },
};
</script>

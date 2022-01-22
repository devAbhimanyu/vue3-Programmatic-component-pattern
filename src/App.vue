<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs

import TypographyStatefulVue from "./components/Typography.stateful.vue";
import TypographyFunctionalVue from "./components/Typography.functional.vue";
</script>

<template>
  <TypographyFunctionalVue
    :as="'h1'"
    class="border margin"
    :font-weight="'bold'"
    :style="{ color: 'green' }"
  >
    This is a functional component
  </TypographyFunctionalVue>
  <TypographyStatefulVue
    :as="'p'"
    class="border margin"
    :font-weight="'light'"
    :style="{ fontStyle: 'italic', color: 'gray' }"
  >
    This is a stateful component
  </TypographyStatefulVue>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.border {
  border: 1px #2c3e50 solid;
  width: 200px;
}

.margin {
  margin: auto;
}
</style>

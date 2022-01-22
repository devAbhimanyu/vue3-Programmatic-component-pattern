<template>
  <component :is="$props.as" :class="classes" :style="$props.style">
    <slot></slot>
  </component>
</template>

<script lang="ts">
import { computed, CSSProperties, defineComponent, h, PropType } from "vue";

export default defineComponent({
  name: "Typography",
  props: {
    as: {
      type: String as PropType<"h1" | "h2" | "h3" | "h4" | "h5" | "h6" | "p">,
      default: "p",
    },
    style: {
      type: String as PropType<CSSProperties>,
      default: () => ({}),
    },
    class: {
      type: String,
      default: "",
    },
    fontWeight: {
      type: String as PropType<"bold" | "light">,
      default: "light",
    },
  },
  setup(props) {
    const classes = computed(() => {
      return `${props.fontWeight === "light" ? "light" : "bold"} ${
        props.class
      }`;
    });
    return { classes };
  },
});
</script>

<style lang="scss" scoped>
.bold {
  font-weight: bold;
}
.light {
  font-weight: 400;
}
</style>

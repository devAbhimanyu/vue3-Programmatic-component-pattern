<script lang="ts">
import { computed, CSSProperties, defineComponent, h, PropType } from "vue";

export default defineComponent({
  name: "TypographyFunctional",
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
  render() {
    return h(
      this.as,
      {
        class: this.classes,
        style: this.style,
      },
      this.$slots.default?.()
    );
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

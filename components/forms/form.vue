<template>
  <form
    @submit.prevent="submit"
    :event="event"
    :action="action"
    :method="method"
    :class="className"
  >
    <slot></slot>
  </form>
</template>

<script>
export default {
  name: "Form",
  props: ["event", "action", "method", "className"],
  data() {
    return {};
  },
  methods: {
    submit() {
      this.$emit(this.$props["event"]);
    },
  },
};
</script>

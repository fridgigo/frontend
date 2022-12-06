<template>
  <div :className="className">
    <h1 class="h4 text-center">{{ header }}</h1>
    <p class="text-muted h5">{{ subheader }}</p>
    <hr>
  </div>
</template>

<script>
import mainButton from "../buttons/main-button.vue";
export default {
  name: "SubBanner",
  components: { mainButton },
  props: ["header", "subheader", "className"],
};
</script>

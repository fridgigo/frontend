<template>
  <div class="banner container text-center mt-5">
    <h1 class="mb-2">Welcome to fridgiGO</h1>
    <p class="text-muted h5">
      Recipes, community, cooking experiments & more... More than XXX recepies
      are waiting for you
    </p>

    <mainButton
      title="Join us"
      link="auth"
      className="btn btn-outline-success bg-green p-2 pl-3 pr-3 ml-1 full-rounded border-0 shadow-sm mt-3 mb-3"
      linkClassName="text-white"
    />
  </div>
</template>

<script>
import mainButton from "../buttons/main-button.vue";
export default {
  name: "Banner",
  components: { mainButton },
};
</script>

<style scoped>
.full-rounded {
    border-radius: 40px;
}
</style>

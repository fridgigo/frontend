<template>
  <div class="footer bg-green w-100 p-2">
    <div class="container text-center">
      <span class="h6 text-white font-weight-bold"
        >&copy; {{ year }} - {{ brandBegin }}</span
      ><span class="font-weight-bold">{{ brandEnd }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Footer",
  data() {
    return {
      brandBegin: "fridgi",
      brandEnd: "GO",
      year: new Date().getFullYear(),
    };
  },
};
</script>

<style coped>
.footer {
  position: absolute;
  bottom: 0;
  margin-top: 50px;
}
</style>

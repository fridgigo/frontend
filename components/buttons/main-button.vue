<template>
  <button :class="className">
    <nuxt-link v-if="link" :to="link" :class="linkClassName">{{
      title
    }}</nuxt-link>
    <span v-else class="link-button">{{ title }}</span>
  </button>
</template>

<script>
export default {
  name: "main-button",
  props: ["link", "title", "className", "linkClassName"],
};
</script>

<style scoped>
.btn-outline-success {
  color: #82d8be;
  border-color: black;
}
.btn-outline-success:hover,
.btn-outline-success:focus,
.btn-outline-success:active {
  background-color: #82d8be !important;
  border-color: #82d8be !important;
}
.btn-outline-success:hover .link-green ,
.btn-outline-success:focus .link-green ,
.btn-outline-success:active .link-green {
  color: white;
}
.link-green {
  color: black;
}
.link-green:hover {
  color: white;
  text-decoration: none;
}
</style>

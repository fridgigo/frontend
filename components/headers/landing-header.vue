<template>
  <div class="header bg-white p-3 sticky-top">
    <div class="container">
      <div class="row">
        <div class="col-1">
          <nuxt-link to="/">
            <img
              src="@/static/images/fridgigo.jpg"
              class="logo"
              alt="fridgiGO brand"
            />
          </nuxt-link>
        </div>
        <div class="col-11 text-right">
          <Button
            class="btn btn-outline-success p-2 pl-3 pr-3 ml-3 full-rounded shadow-sm d-md-none mb-3"
            title="Menu"
            @click="toggle()"
          />
          <nav v-if="menuOpened">
            <nuxt-link to="/" class="text-dark">Home</nuxt-link>
            <nuxt-link to="/about" class="text-dark ml-3">About</nuxt-link>
            <nuxt-link to="/terms-of-services" class="text-dark ml-3"
              >Terms of Services</nuxt-link
            >
            <Button
              title="Sign In"
              link="/auth"
              className="btn btn-outline-success p-2 pl-3 pr-3 ml-3 full-rounded shadow-sm"
              linkClassName="text-dark"
            />
            <Button
              title="Our Community"
              link="community"
              className="btn btn-outline-success bg-green p-2 pl-3 pr-3 ml-1 full-rounded border-0 shadow-sm"
              linkClassName="text-white"
            />
          </nav>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Button from "../buttons/main-button.vue";

export default {
  name: "Header",
  components: { Button },
  data() {
    return {
      menuOpened: true,
    };
  },
  methods: {
    toggle() {
      alert("hello")
      this.menuOpened = !this.menuOpened;
    },
  },
};
</script>

<style scoped>
.full-rounded {
  border-radius: 40px;
}
.text-dark.nuxt-link-exact-active {
  border-bottom: 1px solid rgb(126, 202, 175);
}
.text-dark {
  padding-bottom: 5px;
}
.text-dark:hover {
  border-bottom: 1px solid rgb(126, 202, 175);
}

@media only screen and (max-width: 767px) {
  nav {
    display: flex;
    flex-direction: column;
    text-align: left;
  }
  nav .ml-3 {
    margin-left: 0px !important;
    margin-bottom: 4px;
  }
}
</style>

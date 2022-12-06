<template>
  <div>
    <div class="h-100 body">
      <Header />
      <Banner />
      <hr>
      <MobileApp  />
    </div>
    <Footer />
  </div>
</template>

<script>
import Header from "../components/headers/landing-header.vue";
import Banner from "../components/Banner/banner.vue";
import Footer from "../components/footer/footer.vue";
import MobileApp from "../components/mobile-app/mobile-app.vue"

export default {
  layout: "default",
  name: "IndexPage",
  components: { Header, Footer, Banner, MobileApp },
  head: {
    title: "fridgiGO | Home",
  },
};
</script>

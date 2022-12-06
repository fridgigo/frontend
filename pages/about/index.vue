<template>
  <div>
    <Header />
    <div class="container mt-5 mb-5">
      <SubBanner header="About" />
      <mobileAppVue />
    </div>
    <Footer />
  </div>
</template>

<script>
import Header from "@/components/headers/landing-header.vue";
import Footer from "@/components/footer/footer.vue";
import mobileAppVue from "../../components/mobile-app/mobile-app.vue";
import SubBanner from "../../components/Banner/subBanner.vue";

export default {
  components: {
    Header,
    Footer,
    mobileAppVue,
    SubBanner
  },
  head: {
    title: "fridgiGO | Terms of services",
  },

  data() {
    return {
      header: "About",
    };
  },
};
</script>

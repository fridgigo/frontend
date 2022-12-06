<template>
  <div>
    <Header />
    <div class="container mt-5 mb-5">
        <SubBanner header="Terms of services" />
        <p>Coming soon ...</p>
    </div>
    <Footer />
  </div>
</template>

<script>
import Header from "@/components/headers/landing-header.vue";
import Footer from "@/components/footer/footer.vue";
import SubBanner from "../../components/Banner/subBanner.vue";

export default {
  components: {
    Header,
    Footer,
    SubBanner
  },
  head: {
    title: "fridgiGO | Terms of services",
  },
  data() {
    return {
        header: "Terms of services"
    }
  }
};
</script>

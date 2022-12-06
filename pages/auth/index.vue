<template>
  <div>
    <Header />
    <div
      class="d-flex justify-content-center align-items-center flex-column mt-5 container"
    >
      <h1 class="h3">{{ isUser ? "Login" : "Register" }}</h1>
      <div class="alert alert-danger w-50" v-if="isError">
        {{ errorMessage }}
      </div>
      <Form className="w-50" @authEvent="onSubmit" event="authEvent">
        <TextInput
          v-model="user.email"
          type="email"
          divClass="form-group"
          id="email"
          placeholder="Email address"
          title="Email address"
          className="form-control"
          required="true"
        />
        <TextInput
          v-model="user.password"
          type="password"
          divClass="form-group"
          id="password"
          placeholder="*********"
          title="Password"
          className="form-control"
          required="true"
        />
        <TextInput
          v-model="user.repeatPassword"
          v-if="!isUser"
          type="password"
          divClass="form-group"
          id="repeat-password"
          placeholder="*********"
          title="Repeat password"
          className="form-control"
          required="true"
        />
        <TextInput
          v-model="user.firstName"
          v-if="!isUser"
          type="text"
          divClass="form-group"
          id="first-name"
          placeholder="First name"
          title="First name"
          className="form-control"
          required="true"
        />
        <TextInput
          v-model="user.lastName"
          v-if="!isUser"
          type="text"
          divClass="form-group"
          id="last-name"
          placeholder="Last name"
          title="Last name"
          className="form-control"
          required="true"
        />
        <button class="btn btn-outline-dark">submit</button>
        <hr />
        <p v-if="isUser">
          Don’t have an account yet?
          <span class="btn-link text-dark" @click="changeView">Register</span>
        </p>
        <p v-else>
          Already have an account?
          <span class="btn-link text-dark" @click="changeView">Login</span>
        </p>
      </Form>
    </div>
    <Footer />
  </div>
</template>

<script>
import Form from "../../components/forms/form.vue";
import TextInput from "../../components/form-inputs/text-input.vue";
import Header from "../../components/headers/landing-header.vue";
import Footer from "../../components/footer/footer.vue";
export default {
  name: "auth",
  components: { Form, TextInput, Header, Footer },
  head: { title: "fridgiGO | auth" },
  data() {
    return {
      user: {
        email: "",
        password: "",
        repeatPassword: "",
        firstName: "",
        lastName: "",
      },
      isUser: false,
      isError: false,
      errorMessage: "",
    };
  },
  methods: {
    changeView() {
      this.isUser = !this.isUser;
    },
    onSubmit() {
      if (this.isUser) {
        console.log("login");
      } else {
        console.log("register");
      }
    },
  },
};
</script>

<style scoped>
.btn-link {
  cursor: pointer;
}
</style>

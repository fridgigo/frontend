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
      // every time you change the page, the input fields should be emptied
      this.user.email = "";
      this.user.password = "";
      this.user.repeatPassword = "";
      this.user.firstName = "";
      this.user.lastName = "";

      // change page
      this.isUser = !this.isUser;
    },
    async onSubmit() {
      // user object
      const payload = {
        "email": this.user.email,
        "password": this.user.password,
        "repeat_password": this.user.repeatPassword,
        "first_name": this.user.firstName,
        "last_name": this.user.lastName,
      };
      // request options and params as a object
      const requestOptions = {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
        },
        body: JSON.stringify(payload), // converting JS object to JSON string
      };


      // variables for API
      const loginUri = "https://fridgigo-backend.herokuapp.com/v1/api/users/login";
      const registerUri = "https://fridgigo-backend.herokuapp.com/v1/api/users/register";

      // Login or Register
      if (this.isUser) {
        // check for payload object (input check)
        if ((payload.email != "") & (payload.password != "")) {
          // send a post request with payload as a body of request
          const res = await fetch(loginUri, requestOptions);
          const content = await res.json();
          console.log(content);
        } else {
          this.isError = true;
          this.errorMessage = "Something went wrong. Please try again.";
        }
      } else {
        // check for payload object (input check)
        if (
          (payload.email != "") &
          (payload.first_name != "") &
          (payload.last_name != "") &
          (payload.password != "") &
          (payload.password == payload.repeat_password)
        ) {
          // check if there was an error before
          if (this.isError) {
            this.isError = false;
            this.errorMessage = "";
          }

          // send a post request with payload as a body of request
          const res = await fetch(registerUri, requestOptions);
          const content = await res.json();
          console.log(content);
        } else {
          this.isError = true;
          this.errorMessage = "Something went wrong. Please try again.";
        }
      }
    },
  },
};
</script>

<style scoped>
.btn-link {
  cursor: pointer;
}
.container {
  margin-bottom: 60px;
}
</style>

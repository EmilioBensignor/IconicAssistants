<template>
  <div class="justifyCenter h-100">
    <div class="suiteContent">
      <HeaderOutsideComponent />
      <div class="w-100 heroSuite columnAlignCenter">
        <router-link
          class="d-flex align-center align-self-start ml-5 ma-3"
          :to="routes.LOGIN"
        >
          <v-icon icon="mdi-keyboard-backspace" color="blueViolet"></v-icon>
          <p class="w-100 goBack text-blueViolet ml-1">Go back to Login</p>
        </router-link>
        <h1 class="text-white text-center my-3">Reset Password</h1>
      </div>
      <section class="w-100">
        <p class="text-lila text-center">
          Enter the email address of your account to reset your password
        </p>
        <v-form
          class="w-100 resetPasswordForm columnAlignCenter mt-5"
          v-model="valid"
          @submit.prevent="onSubmit()"
        >
          <div class="w-75 columnAlignCenter ga-2">
            <label class="text-lila align-self-start" for="email">Email</label>
            <v-text-field
              class="w-100"
              id="email"
              v-model="email"
              :rules="emailRules"
            ></v-text-field>
          </div>
          <p class="text-center text-red mt-3" v-if="error">
            {{ error }}
          </p>
          <SecondaryBtnComponent text="Reset Password" :loading="loading" />
        </v-form>
      </section>
    </div>
  </div>
</template>

<script>
import HeaderOutsideComponent from "@/suite/components/HeaderOutsideComponent.vue";
import SecondaryBtnComponent from "@/suite/components/buttons/SecondaryBtnComponent.vue";
import ROUTES_NAMES from "@/router/constants/ROUTES_NAMES";
import { resetPassword } from "../services/auth.service";

export default {
  name: "ResetPasswordView",
  components: {
    HeaderOutsideComponent,
    SecondaryBtnComponent,
  },
  data() {
    return {
      routes: ROUTES_NAMES,
      email: "",
      emailRules: [
        (value) => {
          if (value) return true;

          return "E-mail is requred.";
        },
        (value) => {
          if (/.+@.+\..+/.test(value)) return true;

          return "Invalid email.";
        },
      ],
      valid: false,
      loading: false,
      error: null,
    };
  },
  methods: {
    async onSubmit() {
      if (!this.valid) {
        return;
      }
      this.loading = true;
      await resetPassword(this.email)
        .then(() => {
          this.loading = false;
        })
        .catch(() => (this.loading = false));
    },
  },
};
</script>

<style>
.resetPasswordForm .v-text-field .v-field--no-label input,
.resetPasswordForm .v-text-field .v-field--active input {
  background-color: black;
  color: white;
  border-radius: 0.5rem;
}
</style>

<style scoped>
a {
  text-decoration: none;
}
.goBack {
  font-weight: 500;
}

.secondaryButton:hover {
  color: #373ae6 !important;
}
</style>

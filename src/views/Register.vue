<template>
  <v-container class="cont">
    <v-form @submit.prevent="submitForm" class="form">
      <h1 class="mb-5">Register</h1>
      <v-text-field
        v-model="name"
        label="Name"
        :rules="nameRules"
      ></v-text-field>
      <v-text-field
        v-model="email"
        label="Email"
        type="email"
        :rules="emailRules"
      ></v-text-field>
      <v-text-field
        v-model="password"
        label="Password"
        type="password"
        :rules="passwordRules"
      ></v-text-field>
      <v-text-field
        v-model="confirmPassword"
        label="Confirm Password"
        type="password"
        :rules="confirmPasswordRules"
      ></v-text-field>
      <router-link to="/"> <v-btn type="submit">Sign Up</v-btn></router-link>
    </v-form>
  </v-container>
</template>

<script>
import { ref, computed } from "vue";

export default {
  setup() {
    const name = ref("");
    const email = ref("");
    const password = ref("");
    const confirmPassword = ref("");

    const nameRules = computed(() => [
      (v) => !!v || "Name is required",
      (v) => (v && v.length <= 50) || "Name must be less than 50 characters",
    ]);

    const emailRules = computed(() => [
      (v) => !!v || "Email is required",
      (v) => /.+@.+\..+/.test(v) || "Email must be valid",
    ]);

    const passwordRules = computed(() => [
      (v) => !!v || "Password is required",
      (v) => (v && v.length >= 8) || "Password must be at least 8 characters",
    ]);

    const confirmPasswordRules = computed(() => [
      (v) => !!v || "Confirm Password is required",
      (v) => (v && v === password.value) || "Passwords do not match",
    ]);
  },
};
</script>
<style scoped>
.cont {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 50px;
}
.form {
  width: 400px;
  place-items: center;
}
.signup-form {
  max-width: 400px;
  margin: 0 auto;
}

.signup-form__input {
  margin-bottom: 16px;
}

.signup-form__button {
  margin-top: 16px;
}
</style>
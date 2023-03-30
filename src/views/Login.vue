<template>
  <v-container fluid>
    <v-row justify="center" align="center">
      <v-col cols="12" sm="8" md="4">
        <v-card class="elevation-12">
          <v-toolbar color="dark" dark flat>
            <v-toolbar-title>Login</v-toolbar-title>
          </v-toolbar>
          <v-card-text>
            <v-form @submit.prevent="login">
              <v-text-field
                v-model="email"
                label="Email"
                type="email"
                required
              ></v-text-field>
              <v-text-field
                v-model="password"
                label="Password"
                type="password"
                required
              ></v-text-field>
              <v-btn
                type="submit"
                color="primary"
                class="mr-4 login"
                :loading="loading"
                >Login</v-btn
              >
              <router-link to="/register"
                ><v-btn class="btn" @click="register"
                  >Register</v-btn
                ></router-link
              >
            </v-form>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";

let email = ref("");
let password = ref("");
let loading = ref(false);
const router = useRouter();

const login = function () {
  if (email.value.length > 5 && password.value.length) {
    loading.value = true;
    router.push("/");
    console.log("login");
  }
};
</script>

<style scoped>
.fill-height {
  height: 100%;
}

.text-center {
  text-align: center;
}
.btn {
  background: rgba(0, 0, 0, 0.7);
  color: #fff;
}
.login {
  background: red;
  color: #fff;
}
</style>
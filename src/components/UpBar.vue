<template>
  <v-row class="d-flex align-center position-relative upBar">
    <v-col
      :cols="12"
      :md="3"
      :sm="3"
      class="d-flex justify-center align-center text-center"
    >
      <router-link to="https://olcha.uz/ru">
        <img
          src="data:image/png;base64,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"
          alt="logo"
        />
      </router-link>
    </v-col>
    <v-col :cols="12" :md="3" :sm="3" class="number">
      <v-btn>
        +998 97 733-37-27
        <v-tooltip activator="parent" location="start">Call</v-tooltip>
      </v-btn></v-col
    >
    <v-col :cols="12" :md="3" :sm="3">
      <div class="search d-flex align-center justify-center">
        <input type="text" placeholder="Type something..." />
        <button class="search">Search</button>
      </div>
    </v-col>
    <v-col :cols="12" :md="3" :sm="3" class="linkss">
      <div class="d-block text-center">
        <div class="logins d-flex align-center justify-center">
          <router-link to="/login" class="link mr-5 text-decoration-none"
            >Login</router-link
          >
          <router-link to="/register" class="link text-decoration-none">
            Register</router-link
          >
        </div>
        <div class="cart">
          <router-link to="/cart"> Cart </router-link>
        </div>
        <div class="likes">Likes: 2</div>
      </div>
    </v-col>
  </v-row>
</template>

<script setup>
</script>

<style scoped>
@media (max-width: 960px) {
  .upBar {
    padding-top: 70px;
  }
  .linkss {
    display: flex !important;
  }
}
img {
  width: 130px;
}
h2 {
  font-size: 25px;
}
.search {
  border: 1px solid #000;
  border-radius: 5px;
}
input {
  padding: 5px 10px;
  outline: none;
  width: 100%;
}
button.search {
  background: #000;
  padding: 5px 10px;
  color: #ffffff;
  border-radius: 3px;
}
.logins .link {
  color: #000;
  font-size: 20px;
}
.cart,
.likes {
  font-size: 20px;
}
</style>
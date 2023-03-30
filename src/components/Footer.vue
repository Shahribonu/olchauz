<template>
  <v-footer app color="primary">
    <v-row>
      <v-col cols="12" sm="4">
        <h3>About Us</h3>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed euismod
          est quis eros bibendum, quis ultrices leo fringilla.
        </p>
      </v-col>
      <v-col cols="12" sm="4">
        <h3>Contact Us</h3>
        <p>
          123 Main Street<br />Anytown, USA 12345<br />Phone: (123) 456-7890<br />Email:
          info@example.com
        </p>
      </v-col>
      <v-col cols="12" sm="4">
        <h3>Follow Us</h3>
        <v-icon-button icon="mdi-facebook" class="mx-2"></v-icon-button>
        <v-icon-button icon="mdi-twitter" class="mx-2"></v-icon-button>
        <v-icon-button icon="mdi-instagram" class="mx-2"></v-icon-button>
      </v-col>
    </v-row>
    <v-divider></v-divider>
    <v-row align="center" justify="center">
      <span
        >&copy; {{ new Date().getFullYear() }} My Company. All rights
        reserved.</span
      >
    </v-row>
  </v-footer>
</template>

<script>
import { defineComponent } from "vue";
import { VFooter, VRow, VCol, VDivider, VIconButton } from "vuetify";

export default defineComponent({
  name: "MyFooter",
  components: {
    VFooter,
    VRow,
    VCol,
    VDivider,
    VIconButton,
  },
});
</script>

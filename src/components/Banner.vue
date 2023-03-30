<template>
  <v-row class="d-flex justify-center mt-5 mb-5">
    <v-col :cols="12" :md="4" :sm="6">
      <div>
        <h1 class="d-flex justify-center">Company News</h1>
      </div>
      <div class="d-flex justify-center">
        <v-sheet
          class="d-block scroll_bar"
          max-height="400px"
          overflow-y="scroll"
        >
          <v-card
            class="mx-auto mb-3"
            max-width="344"
            v-for="item in items"
            :key="item.id"
          >
            <v-img :src="item.src" height="200px" cover></v-img>

            <v-card-title> Top western road trips </v-card-title>

            <v-card-subtitle> 1,000 miles of wonder </v-card-subtitle>

            <v-card-actions>
              <v-btn color="orange-lighten-2" variant="text"> Explore </v-btn>
              <v-spacer></v-spacer>
              <v-btn
                :icon="show ? 'mdi-chevron-up' : 'mdi-chevron-down'"
                @click="show = !show"
              ></v-btn>
            </v-card-actions>

            <v-expand-transition>
              <div v-show="show">
                <v-divider></v-divider>

                <v-card-text>
                  I'm a thing. But, like most politicians, he promised more than
                  he could deliver. You won't have time for sleeping, soldier,
                  not with all the bed making you'll be doing. Then we'll go
                  with that data file! Hey, you add a one and two zeros to that
                  or we walk! You're going to do his laundry? I've got to find a
                  way to escape.
                </v-card-text>
              </div>
            </v-expand-transition>
          </v-card>
        </v-sheet>
      </div>
    </v-col>

    <v-col :cols="12" :md="8" :sm="6">
      <carousel />
    </v-col>
  </v-row>
</template>

<script setup>
import { ref } from "vue";
import Carousel from "./Carousel.vue";

const show = ref(false);
let items = ref([
  {
    src: "https://cdn.vuetifyjs.com/images/cards/sunshine.jpg",
    title: "Top western road trips ",
    subtitle: "1,000 miles of wonder",
    text: `I'm a thing. But, like most politicians, he promised more than he
              could deliver. You won't have time for sleeping, soldier, not with
              all the bed making you'll be doing. Then we'll go with that data
              file! Hey, you add a one and two zeros to that or we walk! You're
              going to do his laundry? I've got to find a way to escape.`,
  },
  {
    src: "https://cdn.vuetifyjs.com/images/cards/sunshine.jpg",
    title: "Top western road trips ",
    subtitle: "1,000 miles of wonder",
    text: `I'm a thing. But, like most politicians, he promised more than he
              could deliver. You won't have time for sleeping, soldier, not with
              all the bed making you'll be doing. Then we'll go with that data
              file! Hey, you add a one and two zeros to that or we walk! You're
              going to do his laundry? I've got to find a way to escape.`,
  },
  {
    src: "https://cdn.vuetifyjs.com/images/cards/sunshine.jpg",
    title: "Top western road trips ",
    subtitle: "1,000 miles of wonder",
    text: `I'm a thing. But, like most politicians, he promised more than he
              could deliver. You won't have time for sleeping, soldier, not with
              all the bed making you'll be doing. Then we'll go with that data
              file! Hey, you add a one and two zeros to that or we walk! You're
              going to do his laundry? I've got to find a way to escape.`,
  },
]);
</script>

<style scoped>
.scroll_bar {
  min-height: 450px;
  max-height: 900px;
  overflow-y: scroll;
}
</style>
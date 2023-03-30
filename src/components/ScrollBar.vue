<template>
  <v-container>
    <v-row>
      <v-col>
        <v-sheet
          class="d-flex scroll_bar"
          height="50px"
          max-width="100%"
          overflow-x="auto"
        >
          <router-link
            to="#"
            v-for="item in items"
            :key="item.id"
            class="d-flex links justify-center"
            style="min-width: 100px"
          >
            {{ item.text }}
          </router-link>
        </v-sheet>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const items = ref([
      { id: 1, text: "Item 1" },
      { id: 2, text: "Item 2" },
      { id: 3, text: "Item 3" },
      { id: 4, text: "Item 4" },
      { id: 5, text: "Item 5" },
      { id: 6, text: "Item 6" },
      { id: 7, text: "Item 7" },
      { id: 8, text: "Item 8" },
      { id: 9, text: "Item 9" },
      { id: 10, text: "Item 10" },
      { id: 11, text: "Item 7" },
      { id: 12, text: "Item 8" },
      { id: 13, text: "Item 9" },
      { id: 14, text: "Item 10" },
    ]);

    return {
      items,
    };
  },
};
</script>

<style scoped>
.scroll_bar {
  width: 100%;
  overflow: scroll;
  color: #fff;
  align-items: center;
  padding: 0 10px;
}
::-webkit-scrollbar {
  width: 0;
  height: 0;
}
.links {
  color: #000000;
  box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
  margin: 0 5px;
}
</style>
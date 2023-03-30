<template>
  <v-container>
    <h1 class="mt-6 mb-6">New Arrivals</h1>
    <swiper
      :spaceBetween="20"
      :loop="true"
      :pagination="{
        clickable: true,
      }"
      :breakpoints="{
        '640': {
          slidesPerView: 2,
          spaceBetween: 20,
        },
        '768': {
          slidesPerView: 3,
          spaceBetween: 20,
        },
        '1024': {
          slidesPerView: 4,
          spaceBetween: 20,
        },
      }"
      :navigation="true"
      :modules="modules"
      class="mySwiper mb-5 p-5"
    >
      <swiper-slide v-for="item in items" :key="item.id">
        <product :item="item" />
      </swiper-slide>
    </swiper>

    <h1 class="mt-6 mb-6">Recommendation</h1>
    <swiper
      :spaceBetween="20"
      :loop="true"
      :pagination="{
        clickable: true,
      }"
      :breakpoints="{
        '640': {
          slidesPerView: 2,
          spaceBetween: 20,
        },
        '768': {
          slidesPerView: 3,
          spaceBetween: 20,
        },
        '1024': {
          slidesPerView: 4,
          spaceBetween: 20,
        },
      }"
      :navigation="true"
      :modules="modules"
      class="mySwiper mb-5"
    >
      <swiper-slide v-for="item in items" :key="item.id">
        <product :item="item" />
      </swiper-slide>
    </swiper>
  </v-container>
</template>
<script>
import Product from "./Product.vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import { ref } from "vue";
import "swiper/css";
import "swiper/css/pagination";
import "swiper/css/navigation";
import { Pagination, Navigation } from "swiper";

export default {
  components: {
    Swiper,
    SwiperSlide,
    Product,
  },
  setup() {
    return {
      modules: [Pagination, Navigation],
      items: ref([
        {
          id: 1,
          src: "https://source.unsplash.com/featured/300x200",
          price: "233",
          name: "Samsung",
        },
        {
          id: 2,
          src: "https://source.unsplash.com/featured/300x201",
          price: "233",
          name: "Samsung1",
        },
        {
          id: 3,
          src: "https://source.unsplash.com/featured/300x202",
          price: "233",
          name: "Samsung2",
        },
        {
          id: 4,
          src: "https://source.unsplash.com/featured/300x203",
          price: 233,
          name: "Samsung2",
        },
        {
          id: 5,
          src: "https://source.unsplash.com/featured/300x204",
          price: 233,
          name: "Samsung2",
        },
        {
          id: 6,
          src: "https://source.unsplash.com/featured/300x205",
          price: 233,
          name: "Samsung2",
        },
        {
          id: 7,
          src: "https://source.unsplash.com/featured/300x206",
          price: 233,
          name: "Samsung2",
        },
      ]),
    };
  },
};
</script>

<style scoped>
.swiper {
  width: 100%;
  height: 100%;
}
.swiper-slide {
  text-align: center;
  font-size: 18px;
  background: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
}
.swiper-slide img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.swiper {
  margin-left: auto;
  margin-right: auto;
}
</style>
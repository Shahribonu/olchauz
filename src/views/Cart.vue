<template>
  <v-container>
    <h1 class="text-h2 mb-6">Cart</h1>
    <v-card>
      <v-list>
        <v-list-item-group>
          <v-list-item v-for="product in cartItems" :key="product.id">
            <v-list-item-avatar>
              <v-img :src="product.src" contain class="img"></v-img>
            </v-list-item-avatar>
            <v-list-item-content>
              <v-list-item-title>{{ product.name }}</v-list-item-title>
              <v-list-item-subtitle>{{ product.price }}</v-list-item-subtitle>
              <v-list-item-actions>
                <v-btn class="delete mt-5" @click="removeFromCart(product)">
                  Delete
                </v-btn>
                <v-btn class="mt-5" color="primary" @click="addToCart(product)"
                  >Add to Cart</v-btn
                >
              </v-list-item-actions>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
      <v-card-actions>
        <router-link to="/">
          <v-btn color="primary" @click="checkout">Checkout</v-btn>
        </router-link>

        <v-spacer></v-spacer>
        <span>Total: {{ total }}</span>
      </v-card-actions>
    </v-card>
  </v-container>
</template>

<script>
import { ref, computed } from "vue";

export default {
  name: "Cart",
  setup() {
    const cartItems = ref([
      {
        id: 1,
        src: "https://source.unsplash.com/featured/300x200",
        price: "233",
        name: "Samsung",
      },
    ]);

    const removeFromCart = (product) => {
      const index = cartItems.value.findIndex((item) => item.id === product.id);
      cartItems.value.splice(index, 1);
    };

    const addToCart = (product) => {
      cartItems.value.push(product);
    };

    const checkout = () => {
      alert("Thank you for your purchase!");
      cartItems.value = [];
    };

    const total = computed(() => {
      return cartItems.value.reduce((acc, item) => acc + Number(item.price), 0);
    });

    return {
      cartItems,
      removeFromCart,
      addToCart,
      checkout,
      total,
      // products,
    };
  },
};
</script>

<style scoped>
.text-h1 {
  font-weight: bold;
  font-size: 36px;
  margin-bottom: 24px;
}
.img {
  width: 300px;
}
.delete {
  background: red;
  color: #fff;
  margin-right: 10px;
}
</style>

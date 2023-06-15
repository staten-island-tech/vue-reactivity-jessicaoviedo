<script setup>
import { cart } from "./SideCart.js";
import { total } from "./SideCart.js";
</script>

<template>
  <section class="cardsContainer">
    <div class="card">
      <h2>{{ title }}</h2>
      <h3>${{ price }}.00</h3>
      <h4>Released {{ released }}</h4>
      <img :src="image" alt="Movie Poster" />
      <p class="description">{{ description }}</p>
      <button @click="addit" id="buy" class="cartButton">Add to cart</button>
    </div>
  </section>
</template>

<script>
export default {
  name: "InfoCards",
  props: {
    title: String,
    price: Number,
    released: String,
    description: String,
    image: String,
  },

  methods: {
    addit: function () {
      cart.push({
        name: this.title,
        cost: this.price,
        photo: this.image,
      });
      total.value = total.value;
    },
  },
  components: {},
  computed: {
    image: function () {
      return this.image;
    },
  }, 
};
</script>

<style scoped>
.card {
  background-color: #954348;
  margin: 10px auto;
  padding: auto;
  border: 4mm ridge rgba(115, 4, 26, 0.6);
  border-radius: 30px;
}

.home {
  display: flex;
  justify-content: space-around;
  flex-direction: row;
}

img {
  width: 40%;
  border: thick double white;
}

.description {
  text-align: center;
}

.cartButton {
  display: inline-block;
  position: relative;
  height: 3.5rem;
  width: 12rem;
  border-radius: 7px;
  border: 3px solid #520000;
  padding: 0.6em 1.2em;
  text-align: center;
  font-size: 1em;
  font-weight: 500;
  font-family: inherit;
  padding: 5px;
  margin: 20px;
  background-color: #ffc2c2;
  cursor: pointer;
  transition: 0.3s;
}
.cartButton:hover {
  padding-right: 30px;
  padding-left: 3px;
  border-color: white;
}
.cartButton:after {
  content: "\1F6D2	";
  position: absolute;
  opacity: 0;
  top: 14px;
  right: -20px;
  transition: 0.5s;
}

.cartButton:hover:after {
  opacity: 1;
  right: 10px;
}
</style>

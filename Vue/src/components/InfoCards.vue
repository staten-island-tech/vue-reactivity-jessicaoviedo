<template>
  <section class="cardsContainer">
    <div class="card">
      <h2>{{ title }}</h2>
      <h3>{{ watchtime }}</h3>
      <h4>Released {{ released }}</h4>
      <img :src="image" alt="" />
      <p class="description">{{ description }}</p>
      <button class="cartButton">Add to watchlist</button>
    </div>
  </section>
</template>

<script>
export default {
  name: "Card",
  props: {
    title: String,
<<<<<<< HEAD
    watchtime: Number,
=======
    watchtime: String,
>>>>>>> 593034199f93f5a8c32e81c3b5f9d97112f559ac
    released: String,
    description: String,
    image: String,
    button: String,
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
  flex-direction: column;
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

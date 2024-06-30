<template>
  <div @click="isModalOpen = false" class="black-bg" v-if="isModalOpen">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="isModalOpen = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(menu, index) in menus" :key="index" href="">{{ menu }}</a>
  </div>

  <div class="product" v-for="(product, index) in products" :key="index">
    <img class="room-img" :src="products[index].image" />
    <h4 @click="isModalOpen = true">{{ product.title }}</h4>
    <p>{{ product.price }}원</p>
    <button @click="increase(index)">허위매물신고</button>
    <span>신고 수 : {{ product.report }}</span>
  </div>
</template>

<script>
import products from "../data/products";

export default {
  name: "App",

  data() {
    return {
      isModalOpen: false,

      menus: ["Home", "Shop", "About"],

      products,
    };
  },

  methods: {
    increase(index) {
      this.products[index].report++;
    },
  },
};
</script>

<style>
body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  top: 0;
  left: 0;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
  margin-bottom: 20px;

  > a {
    color: white;
    padding: 10px;
  }
}

.product {
  margin-bottom: 20px;
}

.room-img {
  height: 200px;
}
</style>

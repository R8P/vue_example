<template>
  <div id="app">
    <div class="cart">
      <h3>SEPET</h3>
      <ul>
        <li v-for="item in cartList" :key="item.id">{{ item.title }}</li>
      </ul>
      <p v-if="cartList.length === 0" class="warning">Sepetiniz Boş!!!</p>
    </div>
    <Product @addToCart="cartList.push($event)" :prompName="product" v-for="product in productList"
             :key="product.id"/>

  </div>
</template>

<script>
import Product from "@/components/Product";

export default {
  name: 'App',
  components: {
    Product
  },
  data() {
    return {
      productList: [
        {
          id: 1,
          title: "MacBook Pro",
          price: 14000,
          count: 8,
          description: "Açıklama 1"
        },
        {
          id: 2,
          title: "iPhone",
          price: 10000,
          count: 13,
          description: "Açıklama 2"
        },
        {
          id: 3,
          title: "Lenovo",
          price: 8000,
          count: 10,
          description: "Açıklama 3"
        }
      ],
      cartList: []
    }
  }
}
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.warning{
  padding: 10px 0;
  text-align: center;
  color: red;
  font-size: 16px;
  font-weight: bold;
  background: #f3e854;
  width: 325px;
}
</style>

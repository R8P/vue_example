<template>
  <div class="product">
    <strong>Ürün Adı: {{ prompName.title }}</strong>
    <p>Açıklama: {{ prompName.description }}</p>
    <strong>Fiyat: {{ prompName.price }} | Adet: {{ prompName.count }}</strong>
    <button @click="addToCart(prompName)" class="btnEkle">Ürün Ekle</button>
  </div>
</template>

<script>

export default {
  props: ["prompName"],
  methods: {
    addToCart(product) {
      this.$emit('addToCart', product)
    }
  }
}
</script>

<style>
.product {
  border: 2px dashed #666;
  padding: 5px 10px;
  width: 300px;
  margin-bottom: 5px;
}

.product:hover {
  border: 2px solid #666;
  transition: .5s;
}

.btnEkle {
  padding: 10px 20px;
  display: block;
  background: #54b354;
  color: aliceblue;
  border: 1px solid #54b354;
  float: right;
  cursor: pointer;
}

.btnEkle:hover {
  background: #2b8f2b;
  transition: .5s;
}

</style>
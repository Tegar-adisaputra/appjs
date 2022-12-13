<template>
  <div class="card card-product" style="width: 18rem">
    <img :src="'assets/img/' + product.gambar" class="card-img-top" alt="#" />
    <div class="card-body">
      <h5 class="card-title">{{ product.nama }}</h5>
      <p class="card-text">Harga : Rp. {{ product.harga }}</p>
      <a href="#" class="btn btn-success"><b-icon-bag-plus-fill></b-icon-bag-plus-fill> Order</a>
      <a href="#" class="btn btn-success float-end"><b-icon-cart></b-icon-cart> Add to Cart</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardProduct",
  props: ["product"],
};
</script>

<style></style>

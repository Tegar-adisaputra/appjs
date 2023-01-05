<template>
  <div>
    <div class="container d-flex flex-wrap align-items-center">
      <div class="col">
        <div class="row">
          <div class="card card-product d-flex align-item-center justify-content-center" style="width: 18rem" v-for="item in list" v-bind:key="item.id">
            <!-- <img :src="'assets/img/' + product.gambar" class="card-img-top" alt="#" /> -->
            <div class="card-body">
              <h5 class="card-title">{{ item.title }}</h5>
              <p class="card-text">Id : {{ item.id }}</p>
              <p class="card-text">Harga : Rp. {{ item.amount }}</p>
              <router-link class="btn btn-success" :to="'/detail/' + item.id"><b-icon-bag-plus-fill></b-icon-bag-plus-fill> Order</router-link>
              <!-- <a href="#" class="btn btn-success float-end"><b-icon-cart></b-icon-cart> Add to Cart</a> -->
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import VueAxios from "vue-axios";
import Vue from "vue";
Vue.use(VueAxios, axios);
export default {
  name: "CardProduct",

  data() {
    return { list: undefined };
  },

  mounted() {
    Vue.axios.get("http://127.0.0.1:8001/api/transaction").then((resp) => {
      this.list = resp.data.data;
      console.warn(resp.data.data);
    });
  },
};
</script>

<style></style>

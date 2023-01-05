<template>
  <div class="home">
    <NavbarItem />
    <div class="container">
      <HeroItem />
      <div class="row mt-4">
        <div class="col-md-6">
          <h2>Best Seller</h2>
        </div>
        <div class="col-md-6">
          <router-link to="/foods" class="btn btn-success float-end"><b-icon-eye></b-icon-eye> See All </router-link>
        </div>
      </div>
      <div class="row mb-3">
        <div class="col-md-12 mt-4">
          <CardProduct />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import NavbarItem from "@/components/NavbarItem.vue";
import HeroItem from "@/components/HeroItem.vue";
import CardProduct from "@/components/CardProduct.vue";
import Vue from "vue";
import VueAxios from "vue-axios";
import axios from "axios";
Vue.use(VueAxios, axios);

export default {
  name: "HomeView",
  components: {
    NavbarItem,
    HeroItem,
    CardProduct,
  },
  data() {
    return { list: undefined };
  },

  mounted() {
    Vue.axios.get("http://127.0.0.1:8001/api/transaction").then((resp) => {
      this.list = resp.data.data;
      console.warn(resp.data.data);
    });
  },
  // data() {
  //   return {
  //     products: [],
  //   };
  // },
  // methods: {
  //   setProducts(data) {
  //     this.products = data;
  //   },
  // },
  // mounted() {
  //   axios
  //     .get("http://localhost:3000/best-products")
  //     .then((response) => this.setProducts(response.data))
  //     .catch((error) => console.log(error));
  // },
};
</script>

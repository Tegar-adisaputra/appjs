<template>
  <div class="detail">
    <NavbarItem />
    <div class="container">
      <!-- breadcrumb -->
      <div class="row">
        <div class="col mt-2">
          <nav aria-label="breadcrumb">
            <ol class="breadcrumb">
              <li class="breadcrumb-item active" aria-current="page">
                <router-link to="/" class="text-dark">Home</router-link>
              </li>
              <li class="breadcrumb-item active" aria-current="page">
                <router-link to="#" class="text-dark">List</router-link>
              </li>
            </ol>
          </nav>
        </div>
      </div>

      <div class="row mt-3">
        <div class="col-md-6"></div>
        <div class="col-md-6">
          <h2>Title : {{ list.title }}</h2>
          <h3>Amount : {{ list.amount }}</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import NavbarItem from "../components/NavbarItem.vue";
import axios from "axios";
import VueAxios from "vue-axios";
import Vue from "vue";
Vue.use(VueAxios, axios);

export default {
  name: "DetailView",
  components: {
    NavbarItem,
  },
  data() {
    return { list: undefined };
  },
  mounted() {
    Vue.axios.get("http://127.0.0.1:8001/api/transaction/" + this.$route.params.id).then((resp) => {
      this.list = resp.data.data;
      console.warn(resp.data.data);
    });
  },
};
</script>

<style></style>

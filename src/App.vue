<template>
  <div id="app">
    <router-view />
    <FooterItem />
  </div>
</template>

<script>
import FooterItem from "@/components/FooterItem.vue";
import axios from "axios";
import VueAxios from "vue-axios";
import Vue from "vue";
Vue.use(VueAxios, axios);
export default {
  components: {
    FooterItem,
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
};
</script>

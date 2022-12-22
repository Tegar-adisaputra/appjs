<template>
  <div>
    <NavbarItem />
    <h2>Food list</h2>
    <table border="1px">
      <tr>
        <td>id</td>
        <td>title</td>
        <td>amount</td>
        <td>type</td>
      </tr>
      <tr v-for="item in list" v-bind:key="item.id">
        <td>{{ item.id }}</td>
        <td>{{ item.title }}</td>
        <td>{{ item.amount }}</td>
        <td>{{ item.type }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
// @ is an alias to /src
import NavbarItem from "@/components/NavbarItem.vue";
import axios from "axios";
import VueAxios from "vue-axios";
import Vue from "vue";
Vue.use(VueAxios, axios);

export default {
  name: "FoodsView",
  components: {
    NavbarItem,
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

<style></style>

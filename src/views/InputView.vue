<template>
  <div>
    <NavbarItem />
    <p>title</p>
    <input type="text" name="title" v-model="title" /><br />
    <p>amount</p>
    <input type="number" name="amount" v-model="amount" /><br />
    <p>type</p>
    <input type="text" name="type" v-model="type" placeholder="expense/revenue" /><br />
    <button v-on:click="addData()">submit</button>
  </div>
</template>

<script>
import NavbarItem from "@/components/NavbarItem.vue";
import axios from "axios";

export default {
  name: "InputView",
  components: {
    NavbarItem,
  },
  //API
  data() {
    return {
      title: "",
      amount: "",
      type: "",
    };
  },

  methods: {
    async addData() {
      let result = await axios.post("http://127.0.0.1:8001/api/transaction", {
        title: this.title,
        amount: this.amount,
        type: this.type,
      });
      console.warn(result);
    },
  },
  //
};
</script>

<style></style>

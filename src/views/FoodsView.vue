<template>
  <div>
    <NavbarItem />
    <h2>Food list</h2>
  </div>
</template>

<script>
// @ is an alias to /src
import NavbarItem from "@/components/NavbarItem.vue";

export default {
  name: "FoodsView",
  components: {
    NavbarItem,
  },
};
</script>

<style></style>

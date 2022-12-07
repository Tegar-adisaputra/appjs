<template>
  <div class="home">
    <NavbarItem />
    <h1>Home</h1>
  </div>
</template>

<script>
// @ is an alias to /src
import NavbarItem from "@/components/NavbarItem.vue";

export default {
  name: "HomeView",
  components: {
    NavbarItem,
  },
};
</script>

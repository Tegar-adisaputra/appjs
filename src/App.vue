<template>
  <div id="app">
    <router-view />
    <FooterItem />
  </div>
</template>

<script>
import FooterItem from "@/components/FooterItem.vue";
export default {
  components: {
    FooterItem,
  },
};
</script>

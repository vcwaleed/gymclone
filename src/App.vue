<script setup>
import NavbarComponent from "./components/NavbarComponent.vue";
import BannerPage from "./components/BannerPage.vue"
import ChooseUs from "./components/ChooseUs.vue"
</script>

<template>
 <NavbarComponent/>
<BannerPage/>
</template>

<style lang="scss">
@use "../src/styles/variables" as *;
@use "../src/styles/mixins" as *;

html, body {
  margin: 0;
  padding: 0;
  width: 100%;
  min-height: 100vh;
  overflow-x: hidden;
}

#app {
  background-color: $primary-color;
  min-height: 100vh;
  width: 100%;
}

</style>

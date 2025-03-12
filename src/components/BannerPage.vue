<script setup>
</script>

<template>
  <section class="banner">
    <div class="img_con">
      <img src="../assets/banner.jpg" />
    </div>
    <div class="text_con">
      <div>
        <h1>PUSH</h1>
        <h1>THROUGH</h1>
        <h1>THE PAIN</h1>
      </div>
      <h2>EVERY SINGLE DAY</h2>
      <button class="btn">JOIN US</button>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use "sass:color";
@use '../styles/variables' as *;
@use '../styles/mixins' as *;

.banner {
  position: relative;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
  
  .img_con {
    width: 100%;
    height: 100%;
    position: relative;
    
    img {
      width: 100%;
      height: 85%;
      filter: brightness(60%); 
    }
  }

  .text_con {
    position: absolute;
    top: 50%;
    left: 5%;
    transform: translateY(-50%);
    color: $secondary-color;
    h1 {
      color: $secondary-color;
      font-size: 3rem;
      margin: 0;
    }

    h2 {
      color:$text-color;
      font-size: 1.5rem;
    }
    .btn {
      background-color: transparent;
      color: $secondary-color;
      border: 2px solid $secondary-color;
      padding: 8px 24px;
      font-size: 16px;
      border-radius: 20px;
      cursor: pointer;
      transition: 0.3s;
      &:hover {
        background-color: $secondary-color;
        color: $text-color;
      }
    }
  }
}
</style>

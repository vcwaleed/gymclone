<script setup>
import { ref } from 'vue';

const links = [
  { name: 'talhafitness@gmail.com', path: '/' ,icon: "fa-solid fa-envelope",},
  { name: '03000909090', path: '/',icon: "fa-solid fa-phone", },
];
const socialLinks = [
  { icon: "fa-brands fa-facebook", url: "https://facebook.com" },
  { icon: "fa-brands fa-twitter", url: "https://twitter.com" },
  { icon: "fa-brands fa-instagram", url: "https://instagram.com" },
  {icon: "fa-brands fa-youtube", url: "https://youtube.com" }
];
const isMenuOpen = ref(false);
const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};
const closeMenu = () => {
  isMenuOpen.value = false;
};
</script>
<template>
  <nav class="navbar">
    <div class="brand">
      <img src="../assets/logogym.png" width="60" height="60" />
    </div>
    <ul class="nav-links" :class="{ 'active': isMenuOpen }">
      <li v-for="(link, index) in links" :key="index" @click="closeMenu">
        <i :class="link.icon"></i>
        <a :href="link.path" class="nav-link">{{ link.name }}</a>
      </li>
    </ul>
    <div class="social-icons">
        <a v-for="(social, index) in socialLinks" :key="index" :href="social.url" target="_blank">
          <i :class="social.icon"></i>
        </a>
      </div>
    <button class="hamburger" @click="toggleMenu">
      <svg viewBox="0 0 100 80" width="25" height="25">
        <rect width="100" height="15" rx="8"></rect>
        <rect y="30" width="100" height="15" rx="8"></rect>
        <rect y="60" width="100" height="15" rx="8"></rect>
      </svg>
    </button>
  </nav>
</template>

<style lang="scss" scoped>
@use "sass:color";
@use '../styles/variables' as *;
@use '../styles/mixins' as *;
.navbar {
  display: flex;
  justify-content:space-evenly;
  align-items: center;
  padding: 10px 20px;
  background-color: $primary-color;
  color: $text-color;
  position: sticky;
  top: 0;
  width: auto;
  z-index: 1000;
  .social-icons {
    display: flex;
    gap: 15px;
    margin: 10px 0;

    a {
      color: $secondary-color;
      font-size: 20px;
      transition: color 0.3s ease;

      &:hover {
        color:$text-color;
      }
    }
  }
  .brand {
    display: flex;
    align-items: center;
  }

  .nav-links {
    display: flex;
    gap: 60px;
    list-style: none;
    margin: 0;
    padding: 0;

    li {
      display: flex;
      align-items: center;
      gap: 10px; 
      
      i {
        color: $secondary-color;
        transition: color 0.3s ease;
        font-size: 18px;
      }
    }

    .nav-link {
      color: $secondary-color;
      text-decoration: none;
      font-weight: 500;
      transition: color 0.3s ease;

      &:hover {
        color: $text-color;
        
        & + i {
          color: $text-color;
        }
      }
    }
  }

  .social-icons {
    a i {
      color: $secondary-color;
      transition: color 0.3s ease;
      
      &:hover {
        color: $text-color;
      }
    }
  }


  .hamburger {
    display: none;
    background: none;
    border: none;
    cursor: pointer;
    padding: 0.5rem;
    z-index: 1100;

    svg {
      width: 25px;
      height: 30px;
      rect {
        fill: white;
        transition: fill 0.3s ease;
      }
    }

    &:hover svg rect {
      fill: $secondary-color;
    }
  }

  @include mobile {
    .nav-links {
      position: absolute;
      top: 60px;
      right: 0;
      width: 100%;
      background-color:$primary-color;
      flex-direction: column;
      align-items: center;
      display: none;
      &.active {
        display: flex;
      }
    }
    .hamburger {
      display: block; 
    }
  }
}
</style>
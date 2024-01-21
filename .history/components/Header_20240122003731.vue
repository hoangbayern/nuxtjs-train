<!-- components/AntHeader.vue -->
<template>
    <a-layout-header>
      <a-menu theme="dark" mode="horizontal" :selected-keys="selectedKeys">
        <a-menu-item key="/"><nuxt-link to="/">Home</nuxt-link></a-menu-item>
        <a-menu-item key="/register"><nuxt-link to="/register">Register</nuxt-link></a-menu-item>
        <a-menu-item key="/login"><nuxt-link to="/login">Login</nuxt-link></a-menu-item>
      </a-menu>
    </a-layout-header>
  </template>
  
  <script>
  export default {
    data() {
      return {
        selectedKeys: [this.$route.path],
      };
    },
    watch: {
      $route(to) {
        this.selectedKeys = [to.path];
      },
    },
  };
  </script>
  
  <style scoped>
  /* Styling cho header nếu cần */
  </style>
  
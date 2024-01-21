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
  a-layout-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #001529;
    padding: 0 20px;
  }
  
  a-menu-item {
    margin: 0;
  }
  
  a-menu {
    line-height: 64px;
  }
  
  a-menu-item:hover {
    border-bottom: 2px solid #1890ff;
  }
  
  a-menu-item a {
    color: white;
  }
  
  a-menu-item a:hover {
    color: #1890ff;
  }
  </style>
  
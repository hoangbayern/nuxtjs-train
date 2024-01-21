<template>
    <a-form :form="form" @submit="handleSubmit">
      <a-form-item label="Username" :name="['user', 'name']" :rules="[{ required: true, message: 'Please input your username!' }]">
        <a-input v-model="form.user.name" />
      </a-form-item>
      <a-form-item label="Password" :name="['user', 'password']" :rules="[{ required: true, message: 'Please input your password!' }]">
        <a-input type="password" v-model="form.user.password" />
      </a-form-item>
      <a-form-item>
        <a-button type="primary" html-type="submit">Log in</a-button>
      </a-form-item>
    </a-form>
  </template>
  
  <script>
  export default {
    data() {
      return {
        form: this.$form.createForm(this),
      };
    },
    methods: {
      handleSubmit() {
        this.form.validateFields((err, values) => {
          if (!err) {
            // Xử lý đăng nhập ở đây, có thể gửi dữ liệu lên server hoặc thực hiện các thao tác cần thiết.
            console.log('Received values:', values);
          }
        });
      },
    },
  };
  </script>
  
<template>
    <a-form :form="form" @submit="handleSubmit" class="login-form">
      <a-form-item label="Username">
        <a-input v-decorator="['username', { rules: [{ required: true, message: 'Username requied!' }] }]" />
      </a-form-item>
      <a-form-item label="Password">
        <a-input type="password" v-decorator="['password', { rules: [{ required: true, message: 'Password required!' }] }]" />
      </a-form-item>
      <a-form-item>
        <a-button type="primary" html-type="submit" class="login-form-button">Log in</a-button>
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
      handleSubmit(e) {
        e.preventDefault();
        this.form.validateFields((err, values) => {
          if (!err) {
            console.log('Received values:', values);
            // Xử lý đăng nhập ở đây, có thể gửi dữ liệu lên server hoặc thực hiện các thao tác cần thiết.
          }
        });
      },
    },
  };
  </script>
  
  <style scoped>
  .login-form {
    max-width: 300px;
    margin: auto;
  }
  
  .login-form-button {
    width: 100%;
  }
  </style>
  
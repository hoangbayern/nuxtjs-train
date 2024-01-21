<template>
    <a-form :form="form" @submit="handleSubmit" class="register-form">
      <a-form-item label="Username">
        <a-input v-decorator="['username', { rules: [{ required: true, message: 'Please input your username!' }] }]" />
      </a-form-item>
      <a-form-item label="Email">
        <a-input v-decorator="['email', { rules: [{ required: true, message: 'Please input your email!' }] }]" />
      </a-form-item>
      <a-form-item label="Password">
        <a-input type="password" v-decorator="['password', { rules: [{ required: true, message: 'Please input your password!' }] }]" />
      </a-form-item>
      <a-form-item>
        <a-button type="primary" html-type="submit" class="register-form-button">Register</a-button>
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
            
          }
        });
      },
    },
  };
  </script>
  
  <style scoped>
  .register-form {
    max-width: 300px;
    margin: auto;
  }
  
  .register-form-button {
    width: 100%;
  }
  </style>
  
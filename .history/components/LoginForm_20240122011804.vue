<!-- components/FormLogin.vue -->
<template>
  <a-form :form="form" @submit="handleSubmit" class="login-form">
    <a-form-item label="Username">
      <a-input v-decorator="['username', { rules: [{ required: true, message: 'Username required!' }] }]" />
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
import axios from 'axios';

export default {
  data() {
    return {
      form: this.$form.createForm(this),
    };
  },
  methods: {
    async handleSubmit() {
      try {
        const values = await this.form.validateFields();

        const response = await axios.post('https://86x07hia9j.execute-api.us-east-1.amazonaws.com/Dev/login', values);
        console.log('API Response:', response.data);

        // Xử lý kết quả trả về từ API ở đây
      } catch (error) {
        console.error('API Error:', error);
        // Xử lý lỗi từ API ở đây
      }
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

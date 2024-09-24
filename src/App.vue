<template>
  <div id="app">
    <LoginForm v-if="isLoginPage" @switchToRegister="showRegister" />
    <RegisterForm v-else @switchToLogin="showLogin" />
  </div>
</template>

<script>
import LoginForm from './components/LoginForm.vue';
import RegisterForm from './components/RegisterForm.vue';

export default {
  components: {
    LoginForm,
    RegisterForm
  },
  data() {
    return {
      isLoginPage: true // เริ่มต้นที่หน้า Login
    };
  },
  methods: {
    showRegister() {
      this.isLoginPage = false; // แสดงหน้า Register
    },
    showLogin() {
      this.isLoginPage = true; // แสดงหน้า Login
    }
  }
};
</script>

<style>
/* คุณสามารถเพิ่มสไตล์ของคุณที่นี่ */
</style>

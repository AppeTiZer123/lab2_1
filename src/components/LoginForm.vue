<template>
  <div class="container">
    <h1>เข้าสู่ระบบ</h1>
    <form @submit.prevent="handleLogin"> <!-- ป้องกันการส่งฟอร์ม -->
      <label for="username">ชื่อผู้ใช้:</label>
      <input type="text" v-model="username" id="username" required />

      <label for="password">รหัสผ่าน:</label>
      <input type="password" v-model="password" id="password" required />

      <button type="submit">เข้าสู่ระบบ</button>

      <p>ยังไม่มีบัญชี? <a href="#" @click.prevent="$emit('switchToRegister')">สมัครสมาชิก</a></p>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: ''
    };
  },
  methods: {
    handleLogin() {
      // ตัวอย่างการตรวจสอบข้อมูลผู้ใช้
      if (this.username === 'admin' && this.password === 'password') {
        alert('เข้าสู่ระบบสำเร็จ!');
        // นำทางไปยัง booking.html หรือหน้าอื่น ๆ
        window.location.href = 'booking.html';
      } else {
        alert('ชื่อผู้ใช้หรือรหัสผ่านไม่ถูกต้อง');
      }
    }
  }
};
</script>

<style scoped>
.container {
  max-width: 300px;
  margin: auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

h1 {
  text-align: center;
}

label {
  display: block;
  margin: 10px 0 5px;
}

input {
  width: 100%;
  padding: 8px;
  margin-bottom: 15px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

button {
  width: 100%;
  padding: 10px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}

p {
  text-align: center;
}
</style>

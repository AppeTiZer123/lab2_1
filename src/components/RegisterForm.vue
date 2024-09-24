<template>
    <div class="container">
      <h1>ระบบจองห้องประชุม</h1>
      <form @submit.prevent="handleRegister">
        <label for="fname">ชื่อ:</label>
        <label for="lname">นามสกุล:</label>
        <input type="text" id="fname" v-model="fname" required />
        <input type="text" id="lname" v-model="lname" required />
  
        <label for="email">E-mail:</label>
        <label for="phone">โทร:</label>
        <input type="email" id="email" v-model="email" required />
        <input type="tel" id="phone" v-model="phone" required />
  
        <label for="department">แผนก:</label>
        <label for="position">ตำแหน่ง:</label>
        <select id="department" v-model="department" required>
          <option value="marketing_department">ฝ่ายการตลาด</option>
          <option value="accounting_department">แผนกบัญชี</option>
          <option value="hr_department">ฝ่ายบุคคล</option>
          <option value="customer_service">แผนกบริการลูกค้า</option>
          <option value="ceo">CEO</option>
        </select>
        <select id="position" v-model="position" required>
          <option value="manager">Manager</option>
          <option value="staff">พนักงานทั่วไป</option>
          <option value="hr_manager">Manager ฝ่ายบุคคล</option>
          <option value="customer_service_manager">Manager แผนกบริการลูกค้า</option>
          <option value="executive_secretary">Executive Secretary</option>
        </select>
  
        <label for="username">ชื่อผู้ใช้:</label>
        <input type="text" id="username" v-model="username" required class="full-width" />
  
        <label for="password">รหัสผ่าน:</label>
        <input type="password" id="password" v-model="password" required class="full-width" />
  
        <label for="confirm_password">ยืนยันรหัสผ่าน:</label>
        <input type="password" id="confirm_password" v-model="confirmPassword" required class="full-width" />
  
        <button type="submit">สมัครสมาชิก</button>
  
        <p>มีบัญชีอยู่แล้ว? <a href="#" @click.prevent="$emit('switchToLogin')">เข้าสู่ระบบ</a></p>
      </form>
    </div>
</template>
  
<script>
export default {
    data() {
      return {
        fname: '',
        lname: '',
        email: '',
        phone: '',
        department: '',
        position: '',
        username: '',
        password: '',
        confirmPassword: ''
      };
    },
    methods: {
      handleRegister() {
        if (this.password !== this.confirmPassword) {
          alert('รหัสผ่านไม่ตรงกัน');
          return;
        }
        alert('สมัครสมาชิกสำเร็จ!');
        window.location.href = 'login.html';
      }
    }
};
</script>
  
<style scoped>
body {
    font-family: Arial, sans-serif;
    background-color: #2C2C2C;
    color: #FFF;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    padding: 20px; /* เพิ่ม padding ให้กับ body */
}

.container {
    background-color: #3E3E3E;
    padding: 30px; /* เพิ่ม padding ภายใน container */
    border-radius: 8px;
    width: 500px; /* ขยายความกว้างของฟอร์ม */
    display: flex; /* ใช้ flexbox */
    flex-direction: column; /* ตั้งแนวในแนวตั้ง */
    align-items: center; /* จัดให้อยู่ตรงกลางในแนวนอน */
}

h1 {
    text-align: center;
    color: #D4AF37;
    margin-bottom: 30px; /* เพิ่มระยะห่างด้านล่างของหัวเรื่อง */
}

form {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px 30px; /* เพิ่มระยะห่างระหว่างฟิลด์ */
    width: 100%; /* ให้ฟอร์มขยายเต็มความกว้าง */
}

label {
    margin-bottom: 5px;
    color: #D4AF37;
}

input,
select {
    padding: 12px; /* เพิ่ม padding ให้ฟิลด์ข้อมูล */
    border: none;
    border-radius: 4px;
    width: 100%;
}

.full-width {
    grid-column: span 2;
}

button {
    grid-column: span 2;
    background-color: #D4AF37;
    color: #000;
    padding: 15px; /* เพิ่มขนาดปุ่ม */
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 18px; /* ขยายขนาดตัวอักษรในปุ่ม */
    margin-top: 15px; /* เพิ่มระยะห่างด้านบนของปุ่ม */
}

button:hover {
    background-color: #B5962F;
}

p {
    text-align: center;
    grid-column: span 2;
    margin-top: 20px; /* เพิ่มระยะห่างด้านบนของข้อความ */
}

a {
    color: #D4AF37;
    text-decoration: none;
}

a:hover {
    text-decoration: underline;
}
</style>

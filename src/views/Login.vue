<template>
  <div class="container row">
    <div class="col text-center "> 
         <h3>ĐĂNG NHẬP</h3>
        <form class="" @submit.prevent="login">
        <input v-model="email" placeholder="Nhập Email" class="form-control mb-2"/>
        <input v-model="password" type="password" placeholder="Nhập mật khẩu" class="form-control mb-2"/>
        <button class="btn btn-success">Đăng nhập</button>
        </form>           
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      email: "",
      password: ""
    };
  },
  methods: {
    async login() {
      const res = await fetch("http://localhost:3000/api/auth/login", {
        method: "POST",
        headers: {
          "Content-Type": "application/json"
        },
        body: JSON.stringify({
          email: this.email,
          password: this.password
        })
      });
      const data = await res.json();
      localStorage.setItem("token", data.token);
      this.$router.push("/");
    },
  }
};
</script>
<script>
export default {
methods: {
name: "LogoutButton",
logout() {
const isConfirmed = confirm("Bạn muốn đăng xuất?");
if(isConfirmed){
localStorage.removeItem("token");
this.$router.push({name:"login"});
}
},
},
};
</script>
<template>
    <button @click="logout" class="btn btn-secondary my-3">Đăng xuất</button>
</template>

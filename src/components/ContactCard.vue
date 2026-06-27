<script>
export default {
props: {
contact: { type: Object, required: true },
},
};
</script>
<template>
<div>
<div class="p-1">
<strong>Tên:</strong>
{{ contact.name }}
</div>
<div class="p-1">
<strong>E-mail:</strong>
{{ contact.email }}
</div>
<div class="p-1">
<strong>Địa chỉ:</strong>
{{ contact.address }}
</div>
<div class="p-1">
<strong>Điện thoại:</strong>
{{ contact.phone }}
</div>
<div class="p-1">
<strong>Liên hệ yêu thích:&nbsp;</strong>
<i v-if="contact.favorite" class="fa-solid fa-circle-check"></i>
<i v-else class="fa-solid fa-circle-xmark"></i>
</div>
<div class="p-1">
<strong>Sở thích:</strong>
<span v-for="hobby in contact.hobbies" :key="hobby" class="badge bg-info mx-1">
{{ hobby }}
</span>
</div>
</div>
</template>
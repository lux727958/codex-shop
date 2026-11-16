<script setup>
defineEmits(['book'])
</script>
<template>
<div class="topline">用当季的美好，款待每一次相聚 <span>SEASONAL FOOD, SIMPLE JOY</span></div>
<header><a class="brand" href="#"><i>❧</i><span>里橄榄<small>OLIVE & TABLE</small></span></a><nav aria-label="主导航"><a class="active" href="#home">首页</a><a href="#menu">时令菜单</a><a href="#story">我们的故事</a><a href="#visit">到店指南</a></nav><button class="reserve" @click="$emit('book')">预订餐桌 <span>↗</span></button></header>
</template>

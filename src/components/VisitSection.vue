<script setup>
defineEmits(['book'])
</script>
<template>
<section class="visit" id="visit"><div class="eyebrow">THERE'S A SEAT FOR YOU</div><h2>下一次相聚，就在橄榄里。</h2><p>午餐、晚餐，或只是给自己一点慢时光。</p><button class="button" @click="$emit('book')">预约你的餐桌 ↗</button><div class="visit-details"><span>☼ 概念营业时间：每日 11:00 – 21:30</span><span>⌖ 门店地址与联系方式即将更新</span></div></section>
</template>

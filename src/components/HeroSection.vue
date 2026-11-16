<script setup>
defineEmits(['book'])
</script>
<template>
<section class="hero" id="home"><div class="hero-copy"><div class="eyebrow"><span></span> GOOD FOOD. GOOD COMPANY.</div><h1>把日子，<br>过成<span class="serif">好食光。</span></h1><p>从农场到餐桌，从一餐到日常。<br>用新鲜的食材、温暖的料理，留住相聚的美好。</p><div class="hero-actions"><a class="button" href="#menu">探索时令菜单 <span>↗</span></a><button class="text-button" @click="$emit('book')">预订一份好时光 <span>→</span></button></div><div class="hero-note"><span class="sun">☼</span><span>顺应时节，认真做饭<small>Fresh ingredients. Made with love.</small></span></div></div><div class="hero-photo"><img src="https://images.unsplash.com/photo-1512621776951-a57141f2eefd?auto=format&fit=crop&w=1400&q=85" alt="新鲜蔬菜、烤南瓜与谷物组成的缤纷季节沙拉"><div class="photo-tag">自然的味道<br><em>Always in season.</em></div><div class="round-seal">FRESH & SEASONAL<br><b>✳</b><br>MADE WITH LOVE</div></div><div class="hero-index">01 <span>—</span> THE SEASONAL TABLE</div></section>
<div class="values"><span>✳ 当季鲜食 <small>SEASONAL</small></span><span>❧ 用心手作 <small>HANDCRAFTED</small></span><span>☼ 自然好味 <small>NATURALLY GOOD</small></span><span>♡ 温暖相聚 <small>TOGETHER</small></span></div>
</template>

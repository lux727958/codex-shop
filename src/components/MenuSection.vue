<script setup>
import { computed, ref } from 'vue'
import { categories, dishes } from '../data/menu.js'

const activeCategory = ref('all')
const visibleDishes = computed(() => dishes.filter(dish => activeCategory.value === 'all' || dish.category === activeCategory.value))
</script>

<template>
  <section id="menu" class="menu-section">
    <div class="section-heading">
      <div>
        <div class="eyebrow">A TASTE OF THE SEASON</div>
        <h2>这个时节，刚刚好<span>。</span></h2>
        <p>让食材说话，让每一口都有值得期待的味道。</p>
      </div>
      <div class="filters" role="group" aria-label="菜品分类">
        <button v-for="category in categories" :key="category.id" :class="{ selected: activeCategory === category.id }" :aria-pressed="activeCategory === category.id" @click="activeCategory = category.id">{{ category.label }}</button>
      </div>
    </div>
    <div class="dish-grid">
      <article v-for="dish in visibleDishes" :key="dish.id" :data-category="dish.category">
        <div class="dish-image"><img loading="lazy" :src="dish.image" :alt="dish.alt"><span>{{ dish.label }}</span></div>
        <div class="dish-title"><h3>{{ dish.name }}</h3><b>¥ {{ dish.price }}</b></div>
        <p>{{ dish.ingredients }}</p>
      </article>
    </div>
    <p class="menu-foot">好味道，随季节而更新 <span>✳</span> 食材与价格为概念展示，实际菜单以门店为准</p>
  </section>
</template>

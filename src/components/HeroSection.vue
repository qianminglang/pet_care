<template>
  <section class="hero">
    <div>
      <h1>让每一次洗护， 都是毛孩子的 快乐 Spa 时光</h1>
      <p>
        专业洗护、美容修剪、温和护理，全程公开透明。我们使用宠物友好型洗护用品，
        提供一对一沟通，让你放心把宝贝交给我们。
      </p>
      <div class="cta">
        <a class="btn btn-primary" href="#booking">立即预约</a>
        <a class="btn btn-secondary" href="#pricing">查看价目表</a>
      </div>
    </div>
    <aside class="hero-card">
      <h3>本周热门套餐</h3>
      <ul>
        <li v-for="item in hotPackages" :key="item">{{ item }}</li>
      </ul>
    </aside>
  </section>
</template>

<script setup>
defineProps({
  hotPackages: {
    type: Array,
    required: true
  }
})
</script>

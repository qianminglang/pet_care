<template>
  <header>
    <div class="container nav">
      <div class="logo">爪爪<span>泡泡</span> Pet Spa</div>
      <nav>
        <a v-for="link in links" :key="link.href" :href="link.href">{{ link.label }}</a>
      </nav>
    </div>
  </header>
</template>

<script setup>
defineProps({
  links: {
    type: Array,
    required: true
  }
})
</script>

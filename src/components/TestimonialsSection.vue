<template>
  <section id="testimonials">
    <h2 class="section-title">客户评价</h2>
    <div class="testimonials">
      <article v-for="item in testimonials" :key="item.name + item.pet" class="testimonial">
        <p class="testimonial-text">“{{ item.text }}”</p>
        <div class="testimonial-meta">
          <strong>{{ item.name }}</strong>
          <span>{{ item.pet }}</span>
        </div>
      </article>
    </div>
  </section>
</template>

<script setup>
defineProps({
  testimonials: {
    type: Array,
    required: true
  }
})
</script>

<template>
  <section id="services">
    <h2 class="section-title">我们的服务</h2>
    <div class="services">
      <article
        v-for="(service, idx) in services"
        :key="service.title"
        class="service"
        :ref="(el) => setCardRef(el, idx)"
      >
        <h4>{{ service.title }}</h4>
        <p>{{ service.description }}</p>
      </article>
    </div>
  </section>
</template>

<script setup>
import { onBeforeUnmount, onMounted, ref } from 'vue'

const props = defineProps({
  services: {
    type: Array,
    required: true
  }
})

const cardRefs = ref([])
let observer = null

const setCardRef = (el, idx) => {
  if (el) {
    cardRefs.value[idx] = el
  }
}

onMounted(() => {
  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('show')
          observer.unobserve(entry.target)
        }
      })
    },
    { threshold: 0.2 }
  )

  cardRefs.value.slice(0, props.services.length).forEach((card, idx) => {
    setTimeout(() => {
      if (card) {
        observer.observe(card)
      }
    }, idx * 120)
  })
})

onBeforeUnmount(() => {
  if (observer) {
    observer.disconnect()
  }
})
</script>

<template>
  <section id="gallery">
    <h2 class="section-title">店内环境实景</h2>
    <div class="gallery-wrap">
      <div class="carousel" aria-label="门店环境轮播图">
        <div class="slides" :style="{ transform: `translateX(-${currentIndex * 100}%)` }" @mouseenter="stopAuto" @mouseleave="startAuto">
          <figure class="slide" v-for="slide in slides" :key="slide.src">
            <img :src="slide.src" :alt="slide.alt" loading="lazy" />
            <figcaption>{{ slide.caption }}</figcaption>
          </figure>
        </div>
        <button class="carousel-btn prev" type="button" aria-label="上一张" @click="handlePrev">‹</button>
        <button class="carousel-btn next" type="button" aria-label="下一张" @click="handleNext">›</button>
      </div>
      <div class="dots" aria-label="轮播指示器">
        <button
          v-for="(_, idx) in slides"
          :key="idx"
          class="dot"
          :class="{ active: idx === currentIndex }"
          type="button"
          :aria-label="`切换到第 ${idx + 1} 张`"
          @click="goTo(idx)"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import { onBeforeUnmount, onMounted, ref } from 'vue'

const props = defineProps({
  slides: {
    type: Array,
    required: true
  }
})

const currentIndex = ref(0)
let timer = null

const goTo = (index) => {
  const length = props.slides.length
  if (!length) {
    return
  }
  currentIndex.value = (index + length) % length
}

const next = () => goTo(currentIndex.value + 1)
const prev = () => goTo(currentIndex.value - 1)

const stopAuto = () => {
  if (timer) {
    clearInterval(timer)
    timer = null
  }
}

const startAuto = () => {
  stopAuto()
  if (props.slides.length > 1) {
    timer = setInterval(next, 3800)
  }
}

const handleNext = () => {
  next()
  startAuto()
}

const handlePrev = () => {
  prev()
  startAuto()
}

onMounted(() => {
  startAuto()
})

onBeforeUnmount(() => {
  stopAuto()
})
</script>

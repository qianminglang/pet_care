<template>
  <HeaderNav :links="navLinks" />

  <main class="container">
    <HeroSection :hot-packages="hotPackages" />
    <ServicesSection :services="services" />
    <PricingSection :pricing-rows="pricingRows" />
    <GallerySection :slides="gallerySlides" />
    <TestimonialsSection :testimonials="testimonials" />
    <StoreSection />
    <BookingSection :service-options="serviceOptions" />
  </main>

  <SiteFooter />
</template>

<script setup>
import HeaderNav from './components/HeaderNav.vue'
import HeroSection from './components/HeroSection.vue'
import ServicesSection from './components/ServicesSection.vue'
import PricingSection from './components/PricingSection.vue'
import GallerySection from './components/GallerySection.vue'
import TestimonialsSection from './components/TestimonialsSection.vue'
import StoreSection from './components/StoreSection.vue'
import BookingSection from './components/BookingSection.vue'
import SiteFooter from './components/SiteFooter.vue'

const navLinks = [
  { href: '#services', label: '服务' },
  { href: '#gallery', label: '环境' },
  { href: '#testimonials', label: '评价' },
  { href: '#pricing', label: '价格' },
  { href: '#store', label: '门店' },
  { href: '#booking', label: '预约' }
]

const hotPackages = [
  '小型犬洗护 + 指甲修剪：¥128',
  '猫咪基础清洁 + 梳毛：¥138',
  '精致美容修剪套餐：¥268',
  '新客到店立减 ¥20'
]

const services = [
  {
    title: '深层洁净洗护',
    description: '按毛发类型定制洗护流程，去油去味，保持皮肤健康与毛发蓬松。'
  },
  {
    title: '宠物美容修剪',
    description: '按犬种与主人喜好设计造型，修脸、修脚、修臀一站式完成。'
  },
  {
    title: '猫咪安抚护理',
    description: '低刺激环境，温和手法，减少应激反应，让猫咪更安心。'
  }
]

const pricingRows = [
  { item: '基础洗护', small: '¥98', medium: '¥138', large: '¥188' },
  { item: '美容修剪', small: '¥158', medium: '¥218', large: '¥288' },
  { item: '深层护理套餐', small: '¥198', medium: '¥258', large: '¥328' }
]

const gallerySlides = [
  {
    src: 'https://images.pexels.com/photos/6568501/pexels-photo-6568501.jpeg?auto=compress&cs=tinysrgb&w=1600',
    alt: '宠物洗护操作区实拍图',
    caption: '洗护操作区：宠物友好分区，温和低刺激'
  },
  {
    src: 'https://images.pexels.com/photos/7210268/pexels-photo-7210268.jpeg?auto=compress&cs=tinysrgb&w=1600',
    alt: '等候休息区实拍图',
    caption: '等候休息区：轻松陪护，猫狗玩具齐全'
  },
  {
    src: 'https://images.pexels.com/photos/5731866/pexels-photo-5731866.jpeg?auto=compress&cs=tinysrgb&w=1600',
    alt: '美容修剪区实拍图',
    caption: '美容修剪区：透明可视，造型前先沟通'
  }
]

const testimonials = [
  {
    name: '李女士',
    pet: '柴犬「团子」',
    text: '美容师特别耐心，沟通得很细，做完造型后毛发顺滑又蓬松。'
  },
  {
    name: '周先生',
    pet: '英短「奶糖」',
    text: '猫咪平时怕生，这次洗护过程很安静，回家后状态也很好。'
  },
  {
    name: '王小姐',
    pet: '比熊「泡芙」',
    text: '预约方便，到店几乎不用等，修剪效果和我给的参考图很接近。'
  }
]

const serviceOptions = ['基础洗护', '美容修剪', '深层护理套餐']
</script>

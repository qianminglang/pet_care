<template>
  <section id="booking" class="booking">
    <div>
      <h2 class="section-title">在线预约</h2>
      <p>填写信息后，我们会在营业时间内尽快与你确认时间。</p>
      <div class="tip" style="margin-top: 14px;">
        营业时间：周一至周日 10:00 - 21:00<br />
        门店地址：幸福路 88 号（示例）<br />
        客服电话：400-123-88888
      </div>
    </div>
    <form @submit.prevent>
      <label for="appointmentTime">预约时间</label>
      <input id="appointmentTime" v-model="form.appointmentTime" type="datetime-local" />

      <label for="name">主人姓名</label>
      <input id="name" v-model="form.name" type="text" placeholder="请输入姓名" />

      <label for="pet">宠物类型</label>
      <select id="pet" v-model="form.pet">
        <option value="狗狗">狗狗</option>
        <option value="猫咪">猫咪</option>
        <option value="其他">其他</option>
      </select>

      <label for="service">预约项目</label>
      <select id="service" v-model="form.service">
        <option v-for="option in serviceOptions" :key="option" :value="option">{{ option }}</option>
      </select>

      <label for="phone">联系电话</label>
      <input id="phone" v-model="form.phone" type="tel" placeholder="请输入手机号" />

      <label for="note">备注</label>
      <textarea id="note" v-model="form.note" placeholder="例如：宠物性格、过敏信息等"></textarea>

      <button class="btn btn-primary" type="submit" style="margin-top: 14px;">提交预约</button>
    </form>
  </section>
</template>

<script setup>
import { reactive } from 'vue'

defineProps({
  serviceOptions: {
    type: Array,
    required: true
  }
})

const getTomorrowAtNine = () => {
  const now = new Date()
  const tomorrowAtNine = new Date(now)
  tomorrowAtNine.setDate(now.getDate() + 1)
  tomorrowAtNine.setHours(9, 0, 0, 0)

  const pad = (num) => String(num).padStart(2, '0')
  const year = tomorrowAtNine.getFullYear()
  const month = pad(tomorrowAtNine.getMonth() + 1)
  const day = pad(tomorrowAtNine.getDate())
  const hours = pad(tomorrowAtNine.getHours())
  const minutes = pad(tomorrowAtNine.getMinutes())

  return `${year}-${month}-${day}T${hours}:${minutes}`
}

const form = reactive({
  name: '',
  pet: '狗狗',
  service: '基础洗护',
  appointmentTime: getTomorrowAtNine(),
  phone: '',
  note: ''
})
</script>

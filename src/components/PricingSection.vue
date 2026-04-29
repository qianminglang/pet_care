<template>
  <section id="pricing">
    <h2 class="section-title">透明价目</h2>
    <div class="pricing">
      <table>
        <thead>
          <tr>
            <th>项目</th>
            <th>小型宠物</th>
            <th>中型宠物</th>
            <th>大型宠物</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="row in pricingRows" :key="row.item">
            <td>{{ row.item }}</td>
            <td>{{ row.small }}</td>
            <td>{{ row.medium }}</td>
            <td>{{ row.large }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>
</template>

<script setup>
defineProps({
  pricingRows: {
    type: Array,
    required: true
  }
})
</script>

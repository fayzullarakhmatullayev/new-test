<template>
  <div class="top__block">
    <div class="item" v-for="item in items" :key="item.id">{{ item.name }}</div>

    <span>selected: N / M</span>
  </div>
</template>

<script setup>
defineProps({
  items: {
    type: Array,
    default: () => []
  }
})
</script>

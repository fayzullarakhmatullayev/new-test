<template>
  <div class="top__block single">{{ item.name }}</div>
</template>

<script setup>
defineProps({
  item: {
    type: Object,
    default: () => ({})
  }
})
</script>

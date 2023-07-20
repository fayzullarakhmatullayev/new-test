<template>
  <div class="list">
    <div
      class="list__items"
      v-for="item in items"
      :key="item.id"
      @click="emit('handleClick', item)"
    >
      {{ item.name }}
    </div>
  </div>
</template>

<script setup>
defineProps({
  items: {
    type: Array,
    default: () => []
  }
})

const emit = defineEmits(['handleClick'])
</script>

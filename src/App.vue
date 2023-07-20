<template>
  <main>
    <div class="container">
      <div class="top">
        <TopLeftBlock :items="selectedItems" />
        <TopRightBlock :item="selectedItem" />
      </div>
      <div class="bottom">
        <BlockItems @handle-click="(item) => handleClick(item, 'left')" :items="itemsLeft" />
        <BlockItems @handle-click="(item) => handleClick(item, 'right')" :items="itemsRight" />
      </div>
    </div>
  </main>
</template>

<script setup>
import { ref } from 'vue'
import BlockItems from './components/BlockItems.vue'
import TopLeftBlock from './components/TopLeftBlock.vue'
import TopRightBlock from './components/TopRightBlock.vue'
import { itemsLeft, itemsRight } from './db'

const selectedItem = ref({})
const selectedItems = ref([])

const handleClick = (item, type) => {
  if (type === 'left') {
    const found = selectedItems.value.find((i) => i.id === item.id)
    if (!found && selectedItems.value.length < 6) {
      selectedItems.value.push(item)
    }
  } else if (type === 'right') {
    selectedItem.value = item
  }
}
</script>

<template>
  <h1>{{ header }}</h1>
  <form
      class="add-item-form"
      @submit.prevent="items.push({id: items.length + 1, label: newItem})"
  >
    <input
        type="text"
        placeholder="Add an item"
        v-model="newItem"
    >
    <label>
      <input type="checkbox" v-model="newItemPriorityHigh">
      High Priority
    </label>
    <button
        class="btn btn-primary"
    >
      Save item
    </button>
  </form>
  <ul>
    <li v-for="({id, label}) in items" :key="id">{{ label }}</li>
  </ul>
</template>

<script setup>
import { ref } from 'vue'

const header = ref('Shopping List App')
const items = ref([
  {id:1, label:'Party hats'},
  {id: 2, label:'board games'},
  {id: 3, label: '20 cups'}
])
const newItem = ref('')
const newItemPriorityHigh = ref(false)
</script>

<style src="./assets/main.css">

</style>

<script setup>
import { defineProps, computed } from "vue"

const props = defineProps({
  books: {
    type: Array,
    required: true,
    default: [],
  },
})

const bookCount = computed(() => {
  return props.books.filter((book) => book.title.length > 0).length
})
</script>

<template>
  <h2 class="text-2xl" v-if="books.length == 0">no todo</h2>
  <h2 class="text-2xl" v-else>now have {{ bookCount }} todo</h2>
</template>

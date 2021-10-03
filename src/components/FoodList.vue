<template>
  <ul>
    <li v-for="(food, index) in foods" :key="`${food}-${index}`">{{ food }}</li>
  </ul>
</template>

<script>
const MAX_FOODS = 5

export default {
  props: {
    foods: { type: Array, default: () => [] },
  },
  watch: {
    foods() {
      if (this.foods.length === MAX_FOODS) {
        this.$emit('stop', 'Lista Cheia!!')
        console.log('tem 5 itens', this.foods.length)
      }
    },
  },
}
</script>

<template>
  <div class="hello">
    <div
      class="w-96 h-96 mx-auto bg-rose-600 rounded-md border-stone-900 shadow-md duration-300"
      :class="count > 0 && 'translate-y-6'"
    ></div>
    <div>{{ count }}</div>
    <div>{{ doubleCount }}</div>
    <button @click="() => count++">add</button>
  </div>
</template>

<script lang="ts" setup>
import { useCountStore } from '@/store/count'
import { storeToRefs } from 'pinia'

const countStore = useCountStore()
const { count, doubleCount } = storeToRefs(countStore)
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>

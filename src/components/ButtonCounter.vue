<script setup>
import { ref } from 'vue'

const counter = ref(0)
const increment = () => {
  counter.value++
}

</script>

<template>
    <div>
        <button @click="increment">Clicked {{ counter }} times</button>
    </div>
</template>
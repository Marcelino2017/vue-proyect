<script setup>

defineProps({
    inicio: Number,
    fin: Number,
    maxLengthPosts: Number
})
const emit = defineEmits(['next', 'preview'])

</script>

<template>
    <div class="btn-group" role="group" aria-label="Basic example">
        <button 
            type="button" 
            class="btn btn-outline-primary"
            @click="emit('preview')"
            :disabled="inicio == 0">Preview {{inicio}}</button> 

        <button 
            type="button" 
            class="btn btn-outline-primary"
            @click="emit('next')"
            :disabled="fin >= maxLengthPosts">Next {{ fin }} </button>
    </div>
</template>
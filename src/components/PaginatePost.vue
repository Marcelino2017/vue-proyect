<script setup>

const emit = defineEmits(['next', 'preview'])

</script>

<template>
    <div class="btn-group" role="group" aria-label="Basic example">
        <button 
            type="button" 
            class="btn btn-outline-primary"
            @click="emit('preview')">Preview</button> 

        <button 
            type="button" 
            class="btn btn-outline-primary"
            @click="emit('next')">Next</button>
    </div>
</template>
<script setup>

//defineProps(['title', 'id','body', 'colorText'])

defineProps({
    title: String,
    id: Number,
    body: {
        type: String,
        default: "Sin descripción"
    }
})

const emit = defineEmits(['changeFavorito'])

</script>

<template>
    <div class="card">
        <div class="card-body">
            <h5 class="card-title">    
                {{ id }} {{ title }}
            </h5>

            <p class="card-text">{{ body }}</p>

            <button 
                @click="emit('changeFavorito', title)" 
                class="btn btn-outline-primary"
            >
                Favorito
            </button>
        </div>
        
    </div>
</template>
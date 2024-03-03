<script setup>
import { ref, computed } from 'vue'
import ButtonCounter from './components/ButtonCounter.vue'
import BlogPost from './components/BlogPost.vue'
import PaginatePost from './components/PaginatePost.vue'
import LoadingSpinner from './components/LoadingSpinner.vue'

const posts = ref([])
const postsXpage = 10
const inicio = ref(0)
const fin = ref(postsXpage)
const loading = ref(true)

const favorito = ref('')

const changeFavorito = (title) => {
  favorito.value = title
}

const next = () => {
  inicio.value = inicio.value + postsXpage
  fin.value = fin.value + postsXpage
  console.log(inicio.value, fin.value);
}

const preview = () => {
  inicio.value = inicio.value - postsXpage
  fin.value = fin.value - postsXpage
  console.log(inicio.value, fin.value);
}

fetch('https://jsonplaceholder.typicode.com/posts')
  .then(response => response.json())
  .then(data => {
    posts.value = data
    console.log(posts.value.length)
  })
  .catch(error => console.error(error))
  .finally(() => {
    loading.value = false
  })

const maxLengthPosts = computed(() => posts.value.length)
</script>

<template class="d-flex flex-column justify-content-center aling-items-center">
  <LoadingSpinner v-if="loading" />
  <div class="container-xl d-flex flex-column justify-content-center aling-items-center" id="app">
      <h1>Vue 3</h1>
      <br>
      <h2>Mis post favoritos: {{ favorito }} </h2>

      <PaginatePost 
        class="mb-2"
        @next="next"
        @preview="preview"
        :inicio="inicio"
        :fin="fin"
        :maxLengthPosts="maxLengthPosts"  
      />

      <BlogPost 
        v-for="post in posts.slice(inicio, fin)" 
        :key="post.id" 
        :title="post.title" 
        :id="post.id" 
        :body="post.body"
        @changeFavorito="changeFavorito"
        class="mb-2"
      />
  </div>
</template>

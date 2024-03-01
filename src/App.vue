<script setup>
import ButtonCounter from './components/ButtonCounter.vue'
import BlogPost from './components/BlogPost.vue'

const posts = [
  { id: 1, title: 'Post 1', body: 'Incididunt ea id sunt consequat 1' },
  { id: 2, title: 'Post 2', body: 'Incididunt ea id sunt consequat 2' },
  { id: 3, title: 'Post 3' }
]

</script>

<template>
<div class="container" id="app">
    <h1>Vue 3</h1>
    <h2>Mis post favoritos</h2>

    <br>
    <ButtonCounter />
    <button-counter />
    <br>

    <BlogPost 
      v-for="post in posts" 
      :key="post.id" 
      :title="post.title" 
      :id="post.id" 
      :body="post.body"
    />

    <!-- <BlogPost 
      title="Post" 
      :id="1" 
      body="Incididunt ea id sunt consequat 1"
    />

    <BlogPost 
      title="Post" 
      :id="2" 
      body="Incididunt ea id sunt consequat 2" 
    />

    <BlogPost 
      title="Post" 
      :id="3"  
    /> -->

</div>
</template>

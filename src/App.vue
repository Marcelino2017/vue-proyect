<script setup>
import ButtonCounter from './components/ButtonCounter.vue'
import BlogPost from './components/BlogPost.vue'
</script>

<template>
<div class="container" id="app">
    <h1>Hola Mundo</h1>
    <br>
    <ButtonCounter />
    <button-counter />
    <br>
    <BlogPost 
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
    />

</div>
</template>

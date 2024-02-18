<script setup lang='ts'>
import { ref } from 'vue';
import { Posts } from '@/type/type'

const posts = ref<Posts[]>([])

</script>

<template>
  <div class="list-container">
    <ul>
      <li v-for="post in posts" :key="post.id">{{ post.desc }}</li>
    </ul>
  </div>
</template>

<style>
ul {
  padding: 0;
  margin: 15% auto;
}

li {
  list-style: none;
  padding: 0;
  margin: 0;
}
</style>

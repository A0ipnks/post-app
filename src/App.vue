<script setup lang="ts">
import PostComp from './components/PostComp.vue';
import ListComp from './components/ListComp.vue';
import { ref } from 'vue';
import { Posts } from '@/type/type';

const posts = ref<Posts[]>([])

</script>

<template>
  <div class="">
    <PostComp />
    <ListComp />
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>

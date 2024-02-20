<script setup lang='ts'>
import { Posts } from '@/type/type'

const props = defineProps<{
  posts: Posts[]
}>()


const deletePost = (id: number) => {
  emits("delete-post", id)
}

const emits = defineEmits(["delete-post"])


</script>

<template>
  <div class="list-container">
    <ul>
      <li v-for="post in props.posts" :key="post.id">{{ post.desc }}
        <button class="delete-post-button" @click="deletePost(post.id)">削除</button>
      </li>
    </ul>
  </div>
</template>

<style>
ul {
  padding: 0;
  margin: 5% auto 0;
}

li {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  margin: 0 auto 5%;
  justify-content: space-between;
  max-width: 400px;
  font-size: 14px;
}

.delete-post-button {
  font-size: 14px;
  padding: 0.2em 0.6em;
}

.delete-post-button:hover {
  background-color: #b84141;
}
</style>

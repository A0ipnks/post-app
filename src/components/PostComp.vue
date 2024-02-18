
<script setup lang='ts'>
import { ref } from 'vue'

const posts = ref<string>("")
const submit = () => {
  console.log(posts.value);
  posts.value = ""
}


</script>

<template>
  <div>
    <form class="form-container">
      <textarea v-model="posts"></textarea>
      <button type="submit" @click.prevent="submit">POST</button>
    </form>
  </div>
</template>

<style scoped>
.form-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}



.form-container button {
  display: block;
  margin-top: 15%;
  background-color: #42d883;
}
</style>

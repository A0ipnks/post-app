
<script setup lang='ts'>
import { ref } from 'vue'

const post = ref("")

const submit = () => {
  if (post.value != "") {
    emits("submit", post.value)
    post.value = ""
  } else {
    alert("入力がありません。")
  }
}

const emits = defineEmits(["submit"])
</script>

<template>
  <div>
    <form class="form-container">
      <textarea v-model="post"></textarea>
      <button @click.prevent="submit" type="submit">POST</button>
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

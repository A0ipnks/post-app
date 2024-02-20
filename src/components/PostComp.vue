
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
      <input type="text" v-model="post">
      <button @click.prevent="submit" type="submit">POST</button>
    </form>
  </div>
</template>

<style scoped>
.form-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 30%;
}

.form-container button:hover {
  background-color: #41B883;
  transition: all .3s ease-in-out;
}


.form-container input[type="text" i] {
  margin: 0 auto 5%;
  padding: 0;
  height: 25px;
}
</style>

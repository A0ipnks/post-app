<script setup lang="ts">
import PostComp from './components/PostComp.vue';
import ListComp from './components/ListComp.vue';
import settingModalComp from './components/settingModalComp.vue';
import { ref } from 'vue';
import { Posts } from '@/type/type';

const posts = ref<Posts[]>([])
let id: number = 0

const submitPost = (post: string) => {
  posts.value.push({ id: id++, desc: post })
}

const deletePost = (id: number) => {
  posts.value = posts.value.filter((t) => t.id !== id)
  console.log(posts.value);
}




const isModal = ref(false)
const openUserSetting = () => {
  isModal.value = true
}


const currentUser = ref("")
const submitUserSetting = (userName: string) => {
  currentUser.value = userName
  isModal.value = false
}
</script>

<template>
  <div class="container">
    <div class="header">
      <button @click="openUserSetting">ユーザー設定</button>
    </div>
    <p v-if="currentUser" class="username"><span>{{ currentUser }}</span>さん、お疲れ様です。</p>

    <Teleport to="body">
      <settingModalComp v-if="isModal" @submit-username="submitUserSetting" />
    </Teleport>
    <PostComp @submit="submitPost" />
    <ListComp :posts="posts" @delete-post="deletePost" />

  </div>
</template>

<style scoped>
.header {
  display: flex;
  justify-content: end;
}

p.username {
  color: #fff;
  display: flex;
  justify-content: flex-end;
  font-size: 14px;
  align-items: baseline;
  margin: 0;
}

p.username span {
  font-size: 18px;
  color: #41B883;
}
</style>

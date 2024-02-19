<script setup lang='ts'>
import { ref } from 'vue';

const userName = ref("")

const emits = defineEmits(["submit-username"])

const submitUsername = () => {
  emits("submit-username", userName.value)
}

</script>

<template>
  <div class="modal-mask">
    <div class="modal-container">
      <div class="modal-header">
        <slot name="header">
          <h3>ユーザー設定</h3>
        </slot>
      </div>
      <div class="modal-body">
        <slot name="body">
          <span>名前を教えてください</span>
          <input type="text" v-model="userName">
        </slot>
      </div>
      <div class="modal-footer">
        <slot name="footer">
          <button @click="submitUsername">OK</button>
        </slot>
      </div>
    </div>
  </div>
</template>


<style scoped>
.modal-mask {
  position: fixed;
  z-index: 9999;
  top: 0;
  left: 0;
  background-color: rgba(8, 8, 8, 0.8);
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal-container {
  background-color: #fff;
  max-width: 300px;
  max-height: 400px;
  width: 70%;
  height: 40%;
  border-radius: 0.5em;
  display: flex;
  flex-direction: column;
  text-align: center;
  justify-content: center;
}

span {
  color: #34495E;
  display: block;
  margin: 0 auto 5%;
}

h3 {
  margin: 0 auto 5%;
  color: #41B883;
}

input {
  background-color: #e5e5e5;
  border: none;
  color: #34495E;
  margin: 0 auto 5%;
  height: 24px;
  width: 50%;
}

.modal-container button {
  transition: all .2s ease-in-out;
}
</style>

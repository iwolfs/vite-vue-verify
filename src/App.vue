<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <!-- <HelloWorld msg="Hello Vue 3 + Vite" /> -->
  <button @click="verifyShow('blockPuzzle')">slider</button>
  <button @click="verifyShow('clickWord')">point</button>
  <Verify
      @success="login"
      :captchaType="captchaType"
      :imgSize="{width:'400px',height:'200px'}"
      ref="verifyRef"
    ></Verify>
</template>

<script setup>
import { ref } from 'vue'
import HelloWorld from './components/HelloWorld.vue'
import Verify from './components/verifition/Verify.vue'

// This starter template is using Vue 3 experimental <script setup> SFCs
// Check out https://github.com/vuejs/rfcs/blob/script-setup-2/active-rfcs/0000-script-setup.md

const verifyRef = ref(null)
const captchaType = ref('')
const login = (params) =>{
  console.log('to login', params)
}
const verifyShow = (type) => {
  captchaType.value = type
  verifyRef.value.show()
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

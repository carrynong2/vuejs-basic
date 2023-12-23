<script setup>
  import {ref, defineProps, onMounted} from "vue"
  const count = ref(0)
  const message = ref("")
  const increaseCounter = () => {
    count.value += 1;
  }
  defineProps({
    messageText: String,
    changeMessage: Function
  })
  onMounted(() => {
    console.log('on mounted at Counter.vue');
  })
</script> 

<template>
  <div>Hello {{ messageText }}</div>
  <div>
    <input type="text" v-model="message">
    <button @click="changeMessage(message)">Change message from counter</button>
  </div>
  <button @click="increaseCounter">Click {{ count }}</button>
</template>
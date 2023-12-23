<script setup>
  import Counter from "./components/Counter.vue"
  import {ref, onMounted} from "vue"
  const message = ref("")
  const changeMessage = (newMessage) => {
    message.value = newMessage
  }
  onMounted(() => {
    console.log('on mounted at App.vue');
  })
</script>

<template>
  <input type="text" v-model="message">
  <Counter :messageText="message" :changeMessage="changeMessage"/>
</template>
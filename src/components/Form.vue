<script setup>
  import {ref, reactive,watch, watchEffect} from "vue"
  const formData = reactive({
    firstname: "",
    lastname: ""
  })
  const fullname = ref("")
  watchEffect(()=> {
      console.log('formData from watchEffect',formData);
      fullname.value = `${formData.firstname} ${formData.lastname}`
  })
  watch(formData, (newForm, oldForm) => {
    console.log('formData from watch', formData);
  }, {immediate: true})
</script>

<template>
  <div>
    <div> Fullname: {{ fullname }}</div>
    <input type="text" v-model="formData.firstname">
    <input type="text" v-model="formData.lastname">
  </div>
</template>
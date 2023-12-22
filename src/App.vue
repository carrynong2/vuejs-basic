<script setup>
  import { reactive } from 'vue';
  const gendersList = ["ชาย", "หญิง", "ไม่ระบุ"]
  const interestsList = ["หนังสือ", "กีฬา", "การเมือง", "เกม"]

  const formData = reactive({
    interests: []
  })

  const submitForm = () => {
    console.log('submitForm');
    console.log('formData ', formData);
    console.log('interests', formData.interests.join(","));
  }
</script>

<template>
  <div>
    <div>
      <label for="">Firstname</label>
      <input type="text" name="firstname" v-model="formData.firstname">
    </div>
    <div>
      <label for="">Lastname</label>
      <input type="text" name="lastname" v-model="formData.lastname">
    </div>
    <div>
      <label for="">Gender</label>
      <div v-for="gender in gendersList">
        <input type="radio" name="gender" :value="gender" v-model="formData.gender">
        {{ gender }}
      </div>
    </div>
    <div>
      <label for="">Interests</label>
      <div v-for="interest in interestsList">
        <input type="checkbox" name="interest" :value="interest" v-model="formData.interests">
        {{ interest }}
      </div>
    </div>
    <div>
      <label for="">Description</label>
      <textarea v-model="formData.description"></textarea>
    </div>
    <button @click="submitForm()">Submit</button>
  </div>
</template>
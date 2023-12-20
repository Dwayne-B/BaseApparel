<template>
    
  <form @submit.prevent="handleSubmit()" class="main_content_form ">
    <input v-model="email"   :class="{'main_content_form_input':true, 'main_content_form_input-error':true, 'error-border':error}" type="email" name="email" id="user_email" placeholder="Email Address">
    

    <button class="main_content_form_input_button"><svg width="12" height="20" viewBox="0 0 12 20" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M1 1L9.83566 9.83566L1 18.6713" stroke="white" stroke-width="2"/>
      </svg>
      </button>
   
   
  </form>
  <p v-show="error" class="error">{{errorMsg}}</p>
  </template>
  <style>


</style>
  <script setup>
  import {ref} from 'vue'
  const email = ref('');
  const error = ref(false);
  const errorMsg ='Please provide a valid email';
  const handleSubmit =()=>{
    const emailRegex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;

    if (!email.value || !emailRegex.test(email.value)) {
    // add error message
    error.value = true;
  } else {
    // handle the case when the email is valid
    error.value = false;
  }
    console.log(email.value)
  }
  </script>
 
<template>
    <form @submit.prevent="handleSignUp">
      <input v-model="email" type="email" placeholder="Email">
      <input v-model="password" type="password" placeholder="Password">
      <button type="submit">Sign Up</button>
    </form>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import { createUserWithEmailAndPassword } from 'firebase/auth';
  import { auth } from '../firebase';
  
  const email = ref('');
  const password = ref('');
  
  const handleSignUp = async () => {
    try {
      await createUserWithEmailAndPassword(auth, email.value, password.value);
      alert('Account created!');
    } catch (error) {
      alert(error.message);
    }
  };
  </script>
<template>
    <form @submit.prevent="handleLogin">
      <input v-model="email" type="email" placeholder="Email">
      <input v-model="password" type="password" placeholder="Password">
      <button type="submit">Login</button>
    </form>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import { signInWithEmailAndPassword } from 'firebase/auth';
  import { auth } from '../firebase';
  import { useRouter } from 'vue-router';
  
  const email = ref('');
  const password = ref('');
  const router = useRouter();
  
  const handleLogin = async () => {
    try {
      await signInWithEmailAndPassword(auth, email.value, password.value);
      router.push('/premium');
    } catch (error) {
      alert(error.message);
    }
  };
  </script>
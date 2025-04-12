<template>
    <div class="social-links">
      <a v-for="link in socials" :href="link.url" target="_blank">
        <img :src="`/icons/${link.platform}.svg`" :alt="link.platform">
      </a>
    </div>
  </template>
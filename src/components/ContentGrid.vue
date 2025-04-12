<template>
    <div class="content-grid">
      <div v-for="item in content" :key="item.id">
        <h3>{{ item.title }}</h3>
        <a :href="item.url">View →</a>
      </div>
    </div>
  </template>
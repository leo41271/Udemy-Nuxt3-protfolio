<template>
  <NuxtLayout>
    <NuxtPage />
  </NuxtLayout>
</template>
<!-- <script setup>
const layout= 'another'
</script> -->
<style>
/* 可以是.XXX-enter-active,對應的>nuxt.config pageTransition: { name: 'XXX', mode: 'out-in' }*/
.page-enter-active,
.page-leave-active {
  transition: all 0.1s;
}

.page-enter-from,
.page-leave-to {
  opacity: 0.5;
  filter: grayscale(1);
}
</style>
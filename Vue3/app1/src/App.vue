<template>
  <!-- toggle button -->
  <button @click="openApp">OPEN 앱</button>
  <div v-if="isOpen">
    <CountApp />
  </div>
</template>

<script setup>
import CountApp from './components/CountApp.vue'
import { ref } from 'vue'

// Count앱을 껐다 키는 기능
const isOpen = ref(false);

function openApp() {
  isOpen.value = !isOpen.value;
}

</script>

<style>

</style>

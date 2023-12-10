<template>
  <div id="app">
    <button @click="openApp">OPEN APP</button>
    <!-- v-if 조건문으로 isOpen이 true일때 CountApp열기 -->
    <div v-if="isOpen">
      <CountApp />
    </div>
  </div>
</template>

<script>
import CountApp from './components/CountApp.vue'

export default {
  name: 'App',
  components: {
    CountApp
  },
  // isOpen으로 초기화
  data() {
    return {
      isOpen: false,
    }
  },
  methods: {
    openApp() {
      this.isOpen = !this.isOpen
    },
  }
}
</script>

<style>
#app {
  margin: 20px;
}
</style>

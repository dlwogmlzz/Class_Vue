<template>
<!-- HTML부분 -->
  <div class="hello">
    <h1 class="lime">{{ lang === "ko" ? "안녕" : msg }} {{ name }}{{ mark }}</h1>
    <input type="text" :value="name" @input="updateName">
  </div> 
</template>

<!-- JS부분 -->
<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    lang: String,
    name: String,
    mark: String
  },
  methods: {
    updateName(e) {
      // 부모 컴포넌트의 함수를 호출, App.vue에서 정의한 update-name 메소드를 받아온다.
      this.$emit('update-name', e.target.value)
    }
  }
  // data() {
  //   return {
  //     name: 'Vue2',
  //     mark: '!?'
  //   }
  // }
}
</script>

<!-- CSS부분 -->
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .lime {
    color: #43dc37;
  }
</style>

<template>
  <div id="app">
    <!-- 
      지금 까지 변수의 이름으로 전달을 해왔다면, 함수를 전달하는 방법이 있다. 
      함수로 전달하기 위해서는 @를 붙여서 이름으로 넘겨주고 그안에 = updateName이라는 함수명을 넣고, 함수를 만든다.
      Vue2에서 함수만드는 방법은 methods: {} 형식으로 만들어준다.
    -->
    <HelloWorld lang="ko" msg="Hi" :name="name" :mark="mark" @update-name="updateName" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      name: 'Vue2V',
      mark: '^^'
    }
  },
  // Vue2에는 this를 써서 가져온다. this.name은 위에 data에 정의한 name을 의미한다.
  // name의 Vue2V를 받은 파라미터로 바꾼다?
  methods: {
    updateName(name) {
      this.name = name
    }
  }
}
</script>

<style>
#app {
  margin: 20px;
}

</style>

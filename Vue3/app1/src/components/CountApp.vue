<template>
<!-- Vue3를 컴포지션 API라고 한다. Vue2보다 유지보수가 편하게 바꼈다.!! -->
<!-- Vue3는 Vue2와 달리 프레그먼트가 필요없이 모두가 부모가된다. -->
  <h1>Count: {{ count }}</h1>
  <!-- @click은 onClick을 의미한다. 함수이름은 {}가 아닌 ""로 넣는다. -->
  <button @click="increase">+</button>
  <button @click="decrease">-</button>
  <hr>
  <h1>User: {{ user.name }}</h1>
  <button @click="changeUser">changeUser</button>
  <h1>lowerCaseUserName: {{ lowerCaseUserName }}</h1>
</template>

<script setup>
// script에 항상 setup을 넣어준다.
// script에 setup을 넣어준다.
// ref는 리액트의 useRef
// lifecycle은 선언을 해줘야한다.(속도개선)
// Vue3는 객체를 쓰려면 reactive로 선언을 해야한다.
// 내가 쓰고자 하는 것만 꺼내서 쓰는 느낌
import { ref, onMounted, onUpdated, onUnmounted, reactive, computed } from 'vue'

// 일반 값변수
const count = ref(0)

// 객체
const user = reactive({
  name: 'Kim',
  age: '33'
});

// setCount(1)과 똑같음. 리액트 setState와 같음
// count.value = 1

// 함수
function increase() {
  count.value++;
}
function decrease() {
  count.value--;
}
function changeUser() {
  user.name = 'Lee',
  user.age = '20'
}

// ref와 computed의 차이
// ref는 useState처럼 그냥 변수라면 
// 이렇게 바꿔주면 ref로 바꿔주기 전의 데이터가 남기때문에 안바뀐다.
const lowerCaseUserName = ref(user.name.toLowerCase());

// computed는 useEffect처리가 들어간 state변수라고 생각하면 된다.
// computed로 만든 lowerCaseUserName은 위에 만든 user의 이름이 바뀌는 것을 인식해서 소문자로 바꿔준다.
// const lowerCaseUserName = computed(() => {
//   return user.name.toLowerCase()
// });

// Vue3 LifeCycle : onBeforeMount, onBeforeUpdate, onBeforeUnmount
onMounted(() => {
  console.log('Mounted');
});

onUpdated(() => {
  console.log('Updated: ', count.value);
});

onUnmounted(() => {
  console.log('Destroyed');
});

</script>

<style lang="scss" scoped>

</style>
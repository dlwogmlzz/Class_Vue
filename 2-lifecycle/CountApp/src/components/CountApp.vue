<template>
	<div>
		<h1>Count: {{ count }}</h1>
		<!-- @click은 onClick을 의미한다. 함수이름은 {}가 아닌 ""로 넣는다. -->
		<button @click="increase">+</button>
		<button @click="decrease">-</button>
	</div>
</template>

<script>
	export default {
		data() {
			// useState 개념
			return {
				count: 0,
			}
		},
		// count를 처리해줄 함수
		methods: {
			increase() {
				this.count++;
			},
			decrease() {
				this.count--;
			},
		},
		// Life Cycle : beforeCreate, beforeMount, beforeUpdate, beforeDestroy
  // 처음 컴포넌트가 생성된 시점
  created() {
    console.log('Created')
  },
  // 처음 컴포넌트가 생성되어 렌더링까지 끝난 시점
  mounted() {
    console.log('Mounted')
  },
  // 컴포넌트가 업데이트 된 시점
  updated() {
    console.log('Updated: ', this.count)
  },
  // 컴포넌트가 죽는 시점
  destroyed() {
    console.log('Destroyed')
  },
}
</script>

<style lang="scss" scoped>

</style>
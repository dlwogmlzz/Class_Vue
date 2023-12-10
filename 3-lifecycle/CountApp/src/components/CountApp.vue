<template>
<!-- Vue2를 options API라고 한다. -->
<!-- options API는 직관적인 반면 코드가 많아지면 유지보수가 힘들어진다. -->
	<div>
		<h1>Count: {{ count }}</h1>
		<!-- @click은 onClick을 의미한다. 함수이름은 {}가 아닌 ""로 넣는다. -->
		<button @click="increase">+</button>
		<button @click="decrease">-</button>
		<hr>
		<h1>User: {{ user.name }}</h1>
		<button @click="changeUser">changeUser</button>
		<button @click="lowerCaseUserName">lowerCaseUserName</button>
	</div>
</template>

<script>
	export default {
		data() {
			// useState 개념
			return {
				count: 0,
				user: {
					name: 'Kim',
					age: '33'
				}
			}
		},
		// useEffect와 똑같은 기능을 하는 computed
		computed: {
			lowerCaseUserName() {
				// toLowerCase는 자바스크립트 문법
				return this.user.name.toLowerCase();
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
			changeUser() {
				this.user.name = 'Lee',
				this.user.age = '20'
			}
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
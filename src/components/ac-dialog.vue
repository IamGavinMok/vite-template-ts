<template>
    <div class="wrapper" @click="onClickBtn" v-text="domStudent.age"></div>
</template>

<script setup>
// import { ref, reactive, toRefs, onBeforeMount, onMounted, watchEffect, computed } from 'vue';
// import { useStore } from 'vuex';
// import { useRoute, useRouter } from 'vue-router';
/**
* 仓库
*/
// const store = useStore();
/**
* 路由对象
*/
// const route = useRoute();
/**
* 路由实例
*/
// const router = useRouter();
//console.log('1-开始创建组件-setup')
/**
* 数据部分
*/

// const data = reactive({})
// onBeforeMount(() => {
//   console.log('2.组件挂载页面之前执行----onBeforeMount')
// })
// onMounted(() => {
//   console.log('3.-组件挂载到页面之后执行-------onMounted')
// })
// watchEffect(()=>{
// })
// // 使用toRefs解构
// // let { } = { ...toRefs(data) } 
// defineExpose({
//   ...toRefs(data)
// })

import { ref, reactive, toRefs, onBeforeMount, onMounted, watchEffect, computed, watch } from 'vue';
const student = {
    name: 'test1',
    age: 19,
}
const domStudent = ref(student);

const onClickBtn = () => {
    const { name , age } = domStudent.value
    console.log(name , age)
}

watchEffect(()=>{
    console.log('12')
})
watch(()=>{})
</script>
<style scoped >
.wrapper {
    width: 100%;
    height: 3rem;
    background-color: aqua;
}
</style>
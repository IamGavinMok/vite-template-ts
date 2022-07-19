<template>
    <div class="wrapper" @click="onClickBtn" v-text="domStudent.age"></div>
</template>

<script>
import { ref, reactive, toRefs, onBeforeMount, onMounted, watchEffect, computed, watch, defineComponent } from 'vue';

export default defineComponent({
    setup() {

        const student = {
            name: 'test1',
            age: 19,
        }
        const domStudent = reactive(student);

        const onClickBtn = () => {
            const { name, age } = domStudent.value
            console.log(name, age)
        }

        watch(
            () => domStudent.age,
            (newVal, Val) => {
              
                console.log(newVal)
                console.log(Val);
            },
            { deep: true });


        const count = computed(()=> +domStudent.age + 100);

        setTimeout(() => {
            console.log('count-1', count.value);
            domStudent.age = 20;
            console.log('count-2', count.value);
        }, 1000)

        return {
            domStudent,
            onClickBtn
        }
    }
})
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

</script>
<style scoped >
.wrapper {
    width: 100%;
    height: 3rem;
    background-color: aqua;
}
</style>
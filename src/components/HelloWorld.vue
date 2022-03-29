<template>
  <div id="hello">我是 hello 组件</div>
  <div>{{ count }}</div>
  ·
  <button @click="count++">addClick</button>
</template>

<script lang="ts" setup>
import {
  ref,
  onBeforeMount,
  onBeforeUpdate,
  onMounted,
  onUpdated,
  onBeforeUnmount,
  onUnmounted,
} from "vue";
console.log("setup");
const count = ref<number>(0);
onBeforeMount(() => {
  let div = document.querySelector("#hello");
  console.log("onBeforeMount创建之前，无法获取DOM", div);
});
onMounted(() => {
  let div = document.querySelector("#hello");
  console.log("onMounted创建完成，获取DOM", div);
});
onBeforeUpdate(() => {
  console.log("更新视图之前========>onBeforeUpdate");
});
onUpdated(() => {
  console.log("更新视图完成========>onUpdated");
});
onBeforeUnmount(() => {
  console.log("卸载之前========>onBeforeUnmount");
});
onUnmounted(() => {
  console.log("卸载完成========>onUnmounted");
});
</script>
<style scoped></style>

<template>
  <div class="layout">
    <Menu ref="menus" @chenxi-click="getList"></Menu>
    <div class="layout-right">
      <Header></Header>
      <Content></Content>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { reactive, ref } from "vue";
import Content from "./Content/index.vue";
import Menu from "./Menu/index.vue";
import Header from "./Header/index.vue";
import { react } from "@babel/types";
// const list = reactive<number[]>([1, 2, 3, 4]);
const getList = (obj: number[]) => {
  console.log("传过来的list", obj);
  console.log(menus.value);
};
const menus = ref(null);
</script>
<style lang="less" scoped>
.layout {
  display: flex;
  height: 100%;
  overflow: hidden;
  &-right {
    flex: 1;
    display: flex;
    flex-direction: column;
  }
}
</style>

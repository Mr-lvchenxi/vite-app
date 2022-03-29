<template>
  <div class="content">
    <div :key="item.name" v-for="item in data">{{ item.name }}</div>
    <!-- <div v-for="item in 100" :key="item" class="content-items">
      <Card :content="`我是第${item}个`" />
    </div> -->
  </div>
</template>

<script lang="ts" setup>
import { reactive } from "vue";
import A from "./A.vue";
import B from "./B.vue";
import C from "./C.vue";

type Tabs = {
  name: string;
  comName: any;
};

const data = reactive<Tabs[]>([
  {
    name: "我是A组件",
    comName: "A",
  },
  {
    name: "我是B组件",
    comName: "B",
  },
  {
    name: "我是C组件",
    comName: "C",
  },
]);
</script>
<style lang="less" scoped>
.content {
  flex: 1;
  margin: 20px;
  border: 1px solid #ccc;
  overflow: auto;
  &-items {
    padding: 20px;
    border: 1px solid #ccc;
  }
}
</style>

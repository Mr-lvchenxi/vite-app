<template>
  <div class="menu">
    菜单区域
    <div>{{ title }}</div>
    <div>{{ data }}</div>
    <div>
      <button @click="clickTap">派发</button>
    </div>
    <Tree :data="treeData" @on-click="getItem" />
  </div>
</template>

<script lang="ts" setup>
import Tree from "../../components/Tree/index.vue";
import { defineProps, reactive } from "vue";
import type { TreeList } from "../../utils/type";

type Props = {
  title?: string;
  data?: number[];
};
const getItem = (item: TreeList) => {
  console.log("item---->", item);
};
const treeData = reactive<TreeList[]>([
  {
    name: "no.1",
    children: [
      {
        name: "no.1-1",
        children: [
          {
            name: "no.1-1-1",
          },
        ],
      },
    ],
  },
  {
    name: "no.2",
    children: [
      {
        name: "no.2-1",
      },
    ],
  },
  {
    name: "no.3",
  },
  {
    name: "no.4",
    children: [],
  },
]);
withDefaults(defineProps<Props>(), {
  title: "我是默认值",
  data: () => [9, 8, 7, 6, 5],
});
const list = reactive<number[]>([6, 6, 6]);

const emit = defineEmits(["chenxi-click"]);
const clickTap = () => {
  emit("chenxi-click", list);
};
defineExpose({
  list,
});
</script>
<style lang="less" scoped>
.menu {
  width: 200px;
  border-right: 1px solid #ccc;
}
</style>

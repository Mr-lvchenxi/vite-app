<template>
  <div style="margin-left: 10px">
    <div
      @click.stop="clickItem(item)"
      :key="index"
      v-for="(item, index) in data"
      style="margin-bottom: 20px"
    >
      {{ item.name }}
      <TreeItem
        @on-click="clickItem"
        v-if="item?.children?.length"
        :data="item.children"
      />
    </div>
  </div>
</template>

<script lang="ts" setup>
import type { TreeList } from "../../utils/type";

type Props = {
  data?: TreeList[];
};

defineProps<Props>();

const emit = defineEmits(["on-click"]);

const clickItem = (item: TreeList) => {
  console.log(item, 22222);
  emit("on-click", item);
};
</script>

<script lang="ts">
export default {
  name: "TreeItem",
};
</script>

<style lang="less" scoped></style>

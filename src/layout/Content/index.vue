<template>
  <div class="content">
    <div v-for="item in 100" :key="item" class="content-items">
      <Card :content="`我是第${item}个`" />
    </div>
  </div>
</template>

<script lang="ts" setup>
import {} from "vue";
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

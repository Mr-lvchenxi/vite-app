<template>
  <div class="card">
    <div class="card-header">
      <div>主标题</div>
      <div>副标题</div>
    </div>
    <div v-if="content" class="card-content">
      {{ content }}
    </div>
  </div>
</template>

<script lang="ts" setup>
import { defineProps } from "vue";
type Props = {
  content?: string;
};
defineProps<Props>();
</script>
<style lang="less" scoped>
@boder: #ccc;
.card {
  border: 1px solid @boder;
  &:hover {
    box-shadow: 0 0 10px @boder;
  }
  &-header {
    display: flex;
    justify-content: space-between;
    border-bottom: 1px solid @boder;
    padding: 10px;
  }
  &-content {
    padding: 10px;
  }
}
</style>

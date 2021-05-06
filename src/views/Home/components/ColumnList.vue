<template>
  <ul>
    <li v-for="column in list" :key="column.id">
      <img :src="column.avatar" :alt="column.title" />
      <p>{{ column.description }}</p>
    </li>
  </ul>
</template>
<script lang="ts">
import { defineComponent, PropType } from "vue";
export interface ColumnProps {
  id: number;
  title: string;
  avatar: string;
  description: string;
}
export default defineComponent({
  name: "ColumnList",
  props: {
    list: {
      type: Array as PropType<ColumnProps[]>, // 将构造函数断言成一个类型需要添加 PropType
      required: true
    }
  }
});
</script>
<style lang=""></style>

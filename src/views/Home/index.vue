<template>
  <div class="home ">
    <ColumnList :list="list"></ColumnList>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ColumnList, { ColumnProps } from "./components/ColumnList.vue";

const testData: ColumnProps[] = [
  {
    id: 1,
    title: "123",
    description: "這是test1專欄",
    avatar: "http://vue-maker.oss-cn-hangzhou.aliyuncs.com/vue-marker/5ee",
  },
  {
    id: 2,
    title: "456",
    description: "這是test2專欄",
    avatar: "http://vue-maker.oss-cn-hangzhou.aliyuncs.com/vue-marker/5ee",
  },
];
export default defineComponent({
  name: "Home",
  components: {
    ColumnList,
    // GobalHeader
  },
  setup() {
    return {
      list: testData,
    };
  },
});
</script>

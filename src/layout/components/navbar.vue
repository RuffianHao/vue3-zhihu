<template>
  <nav class="navbar navbar-dark  bg-primary mb-4" ref="gobalNavRef">
    <div class="container">
      <a class="navbar-brand">之乎者也</a>
      <ul v-if="!user.isLogin" class="list-inline mb-0">
        <li class="list-inline-item">
          <a href="#" class="btn btn-outline-light my-2">登入</a>
        </li>
        <li class="list-inline-item">
          <a href="#" class="btn btn-outline-light my-2">登出</a>
        </li>
      </ul>
      <ul v-else class="list-inline mb-0">
        <li class="list-inline-item">
          <dropdown :title="`你好${user.name}`">
            <dropdown-item>个人资料</dropdown-item>
            <dropdown-item :disabled="true">设置</dropdown-item>
            <dropdown-item>退出</dropdown-item>
          </dropdown>
        </li>
      </ul>
    </div>
  </nav>
</template>
<script lang="ts">
import { defineComponent } from "vue";
import Dropdown from "@/components/Dropdown.vue";
import DropdownItem from "@/components/DropdownItem.vue";
export interface UserProps {
  isLogin: boolean;
  name?: string;
  id?: number;
}
const user: UserProps = {
  isLogin: true,
  name: "123",
};
export default defineComponent({
  name: "GobalHeader",
  components: {
    Dropdown,
    DropdownItem,
  },
  // props: {
  //   user: {
  //     type: Object as PropType<UserProps>,
  //     required: true
  //   }
  // },

  setup() {
    return { user };
  },
});
</script>
<style lang=""></style>

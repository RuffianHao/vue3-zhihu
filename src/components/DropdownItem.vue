<template>
  <a class="dropdown-item" href="#" :class="{ 'is-disabled': disabled }">
    <slot></slot>
  </a>
</template>
<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "DropdownItem",
  props: {
    disabled: {
      type: Boolean,
      default: false
    }
  }
});
</script>
<style lang="scss">
.dropdown-item.is-disabled {
  color: #6c757d !important;
  pointer-events: none;
  background-color: transparent;
}
</style>

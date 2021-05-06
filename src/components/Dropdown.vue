<template>
  <div class="dropdown" ref="dropdownRef">
    <a
      class="btn dropdown-toggle btn-outline-light my-2"
      href="#"
      role="button"
      id="dropdownMenuLink"
      data-toggle="dropdown"
      aria-haspopup="true"
      aria-expanded="false"
      @click.prevent="toggleOpen"
    >
      {{ title }}
    </a>

    <div
      class="dropdown-menu"
      aria-labelledby="dropdownMenuLink"
      :style="{ display: isOpen ? 'block' : 'none ' }"
    >
      <slot></slot>
    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent, ref, watch } from "vue";
import UseClickOutside from "@/hooks/useClickOut.ts";
export default defineComponent({
  name: "Dropdown",
  props: {
    title: {
      type: String,
      required: true
    }
  },
  setup() {
    const isOpen = ref(false);
    const toggleOpen = () => {
      isOpen.value = !isOpen.value;
    };
    const dropdownRef = ref<HTMLElement | null>(null);
    const isClickOut = UseClickOutside(dropdownRef);

    watch(isClickOut, () => {
      if (isClickOut.value && isOpen.value) {
        isOpen.value = false;
      }
    });
    return {
      isOpen,
      toggleOpen,
      dropdownRef
    };
  }
});
</script>

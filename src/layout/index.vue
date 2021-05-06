<template>
  <navbar></navbar>
  <app-main></app-main>
</template>
<script lang="ts">
import { defineComponent } from "vue";
import { Navbar, AppMain } from "./components/index";
export default defineComponent({
  name: "Layout",
  components: { Navbar, AppMain },
});
</script>
<style lang=""></style>

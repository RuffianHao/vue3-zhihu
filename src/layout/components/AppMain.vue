<template>
  <section class="app-main">
    <div class="container">
      <router-view />
    </div>
  </section>
</template>
<script>
export default {
  name: "AppMain",
};
</script>
<style lang="scss" scoped>
.app-main {
  min-height: calc(100vh - 100px);
  width: 100%;
  padding-top: 50px;
  position: relative;
  overflow: hidden;
  box-sizing: content-box;

  .container {
    padding: 0 15px;
    margin: 0 auto;
    box-sizing: content-box;

    @media screen and (min-width: 768px) {
      width: 750px;
    }

    @media screen and (min-width: 992px) {
      width: 970px;
    }

    @media screen and (min-width: 1200px) {
      width: 1170px;
    }
  }
}
</style>

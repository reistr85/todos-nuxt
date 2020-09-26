<template>
  <div class="container">
    <Home />
  </div>
</template>

<script>
import Home from './home';
export default {
  name: 'index',
  components: {
    Home,
  },
};
</script>

<style lang="scss">
.container-nuxt {
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;

  .title {
    margin-top: 25px;
  }

  .content-main {
    margin-top: 35px;
  }
}
</style>

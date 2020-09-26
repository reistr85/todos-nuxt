<template>
  <div class="container container-nuxt">
    <div class="title">
      <h1>Home</h1>
    </div>

    <div class="content-main">
      <Logo />
    </div>
  </div>
</template>

<script>
import Logo from '@/components/Logo';

export default {
  name: 'home',
  components: {
    Logo,
  },
};
</script>

<style lang="scss" scoped></style>

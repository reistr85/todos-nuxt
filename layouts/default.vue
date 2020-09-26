<template>
  <div class="app">
    <NavBarComponent :bg="'primary'" />
    <Nuxt />
  </div>
</template>

<script>
/* eslint-disable semi */
/* eslint-disable quotes */
/* eslint-disable vue/name-property-casing */
/* eslint-disable vue/no-unused-components */

import NavBarComponent from "@/components/NavBarComponent";

export default {
  name: "app",

  components: {
    NavBarComponent
  }
};
</script>

<style>
* {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
}
</style>

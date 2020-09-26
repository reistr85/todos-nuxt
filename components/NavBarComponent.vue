<template>
  <div class="">
    <nav :class="[`navbar navbar-expand-lg navbar-dark bg-${bg}`]">
      <a class="navbar-brand" href="#">Nuxt</a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarNav"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li
            :class="[
              'nav-item',
              {
                active:
                  this.$route.name == 'home' || this.$route.name == 'index',
              },
            ]"
          >
            <nuxt-link :to="{ name: 'index' }" class="nav-link" href="#"
              >Home</nuxt-link
            >
          </li>
          <li
            :class="[
              'nav-item',
              {
                active: this.$route.name == 'empresa',
              },
            ]"
          >
            <nuxt-link :to="{ name: 'empresa' }" class="nav-link" href="#"
              >About</nuxt-link
            >
          </li>
          <li
            :class="[
              'nav-item',
              {
                active: this.$route.name == 'todo',
              },
            ]"
          >
            <nuxt-link :to="{ name: 'todo' }" class="nav-link" href="#"
              >Todos</nuxt-link
            >
          </li>
          <li
            :class="[
              'nav-item',
              {
                active: this.$route.name == 'users',
              },
            ]"
          >
            <nuxt-link :to="{ name: 'users' }" class="nav-link" href="#"
              >Layout Users</nuxt-link
            >
          </li>
        </ul>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'nav-bar',
  props: {
    bg: {
      type: String,
      default: 'primary',
    },
  },

  components: {},
};
</script>

<style lang="scss" scoped></style>

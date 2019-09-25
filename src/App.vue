<template>
  <div id="app">
    <!-- If it is needed, the navbar can be hidden using the navbarIsVisible prop. -->
    <!-- Logic can be implemented based on the current route: this.$router.currentRoute.name -->
    <navbar v-bind:navbarIsVisible="true" />
    <router-view />
  </div>
</template>

<script>
  import navbar from './components/Navbar.vue';

  export default {
    name: 'App',
    components: {
      navbar
    }
  }
</script>

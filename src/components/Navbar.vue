<template>
  <div v-if="navbarShouldBeShown">
    <router-link to="/"> Home </router-link> |
    <router-link to="/about"> About </router-link> |
    <router-link to="/contact"> Contact </router-link>
  </div>
</template>

<script>
  export default {
    data() { return { navbarShouldBeShown: this.navbarIsVisible } },
    mounted() { this.$watch('navbarIsVisible', navbarIsVisible => { this.navbarShouldBeShown = navbarIsVisible }, { immediate: true }) },
    props: ['navbarIsVisible'],
    name: 'navbar'
  };
</script>

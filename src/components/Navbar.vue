<template>
  <nav id="application-navbar" class="navbar navbar-default" role="navigation" v-if="navbarShouldBeShown">
    <div class="container-fluid">
      <div class="navbar-header">
        <button class="navbar-toggle" data-target="#application-navbar-collapse" data-toggle="collapse" type="button">
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
        </button>
        <router-link class="navbar-brand" to="/">
          <img src="../assets/fam-nav-logo.png" />
        </router-link>
      </div>
      <div id="application-navbar-collapse" class="collapse navbar-collapse">
        <ul class="nav navbar-nav"> <!-- Left-aligned links can be rendered from this list. --> </ul>
        <ul class="nav navbar-nav navbar-right">
          <li><router-link to="/"> Home </router-link></li>
          <li><router-link to="/about"> About </router-link></li>
          <li><router-link to="/contact"> Contact </router-link></li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
  export default {
    data() { return { navbarShouldBeShown: this.navbarIsVisible } },
    mounted() { this.$watch('navbarIsVisible', navbarIsVisible => { this.navbarShouldBeShown = navbarIsVisible }, { immediate: true }) },
    props: ['navbarIsVisible'],
    name: 'navbar'
  };
</script>

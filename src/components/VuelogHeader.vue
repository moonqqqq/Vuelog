<template>
  <div class="header-wrap">
    <div class="header">
      <div class="header-logo">
        <a v-link="{path: '/'}">
          <img :src="database.deployment.logo">
          <span v-text="database.deployment.title"></span>
        </a>
      </div>
      <vuelog-search v-if="database.search.enable && (!database.deployment.useHomepage || $route.path !== '/')" :settings="database.search"></vuelog-search>
      <vuelog-navigation :items="database.navigation"></vuelog-navigation>
    </div>
  </div>
</template>

<script>
  import VuelogNavigation from './VuelogNavigation'
  import VuelogSearch from './VuelogSearch'

  export default {
    components: {
      VuelogNavigation,
      VuelogSearch
    },

    props: ['database']
  }
</script>

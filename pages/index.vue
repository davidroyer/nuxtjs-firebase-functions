<template>
  <section class="container">
    <div>
      <logo/>
      <h1 class="title">
        Nuxt.js Firebase Functions
      </h1>
      <h2 class="subtitle">
        Nuxt.js project
      </h2>
      <h4 class="vertical-space">Rendered From:  <span>{{renderSource}}</span></h4>

      <div class="links">
        <a href="https://nuxtjs.org/" target="_blank" class="button--green">Documentation</a>
        <a href="https://github.com/nuxt/nuxt.js" target="_blank" class="button--grey">GitHub</a>
      </div>
    </div>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  asyncData () {
    return {
      renderSource: process.static ? 'static' : (process.server ? 'server' : 'client')
    }
  },
  components: {
    Logo
  }
}
</script>

<style>
</style>

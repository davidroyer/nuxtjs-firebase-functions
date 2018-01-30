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
      <h4 class="render-result vertical-space">Rendered From:  <span>{{renderSource}}</span></h4>
      <ul>
        <li v-for="fact in facts" :key="fact.text">
          {{ fact.text }}
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
import fetch from 'isomorphic-fetch';
import Logo from '@/components/Logo.vue'

export default {
  async asyncData () {
    let response = await fetch('https://nuxt-ssr.firebaseio.com/facts.json');
    let facts = await response.json();
    return {
      facts,
      renderSource: process.static ? 'static' : (process.server ? 'server' : 'client')
    }
  },
  components: { Logo }
}
</script>

<style>
ul {
  padding: 0;
  margin: 0
}
ul li {
  font-size: 18px;
  list-style-type: none;
  height: 48px;
  width: 100%;
  color: rgba(0, 0, 0, .63);
  border-bottom: 1px dashed rgba(0, 0, 0, .42);
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center
}
</style>

<template>
  <section class="container">
    <div>
      <h1 class="title">
        Nuxt.js Firebase Functions
      </h1>
      <h2 class="subtitle">
        Page 2
      </h2>
      <h4 class="vertical-space">Rendered From:  <span>{{renderSource}}</span></h4>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quia at doloribus nesciunt animi sed eum nemo neque dolor ad nihil libero adipisci perspiciatis, error impedit soluta eos quibusdam explicabo ullam culpa repellat quos provident, consequuntur excepturi. Debitis, nostrum, accusamus? Quos obcaecati libero atque ratione placeat praesentium nam odit nulla iusto.</p>
    </div>
  </section>
</template>

<script>
export default {
  asyncData () {
    return {
      renderSource: process.static ? 'static' : (process.server ? 'server' : 'client')
    }
  }
}
</script>

<style>
</style>

<template>
  <div class="view-container">
    <div class="row">
      <Landing></Landing>
      <About></About>
    </div>
    <FeaturedProjects></FeaturedProjects>
    <Experience></Experience>
  </div>
</template>

<style lang="scss">
  @media screen and (min-width: 0px) {
    .view-container {
      .row {
        display: flex;
        flex-direction: column;
      }
    }
  }
  @media screen and (min-width: 768px) {
    .view-container {
      .row {
        flex-direction: row;
        flex-wrap: wrap;
      }
    }
  }
</style>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage'
})
</script>

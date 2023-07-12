<template>
  <div class="view-container">
    <div class="row">
      <Landing></Landing>
      <About></About>
    </div>
    <FeaturedProjects></FeaturedProjects>
    <div class="row">
      <Experience></Experience>
      <Skills></Skills>
    </div>
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
  @media screen and (min-width: 1000px) {
    .view-container {
      width: 1000px;
      margin-left: auto;
      margin-right: auto;
    }
  }
</style>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage'
})
</script>

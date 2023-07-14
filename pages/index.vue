<template>
  <div class="view-container">
    <div class="row">
      <Landing></Landing>
      <About></About>
    </div>
    <FeaturedProjects></FeaturedProjects>
    <div class="row">
      <div class="column">
        <Experience></Experience>
        <div class="hide-mobile">
          <Contact></Contact>
        </div>
      </div>
      <div class="column">
        <Skills></Skills>
        <div class="hide-tablet">
          <Contact></Contact>
        </div>
        <ContactForm></ContactForm>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
  @media screen and (min-width: 0px) {
    .view-container {
      .row {
        display: flex;
        flex-direction: column;
        .column {
          display: flex;
          flex-direction: column;
        }
      }
      .hide-mobile {
        display: none;
      }
      .hide-tablet {
        display: block;
      }
    }
  }
  @media screen and (min-width: 768px) {
    .view-container {
      .row {
        flex-direction: row;
        flex-wrap: wrap;
        .column {
          width: calc(50% - 1rem);
        }
      }
      .hide-mobile {
        display: block;
      }
      .hide-tablet {
        display: none;
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

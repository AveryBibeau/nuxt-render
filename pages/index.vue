<template>
  <div class="index">
    <p>SSR random(): {{ random }}</p>
    <p>SSR query: {{ query }}</p>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
  data() {
    return {
      random: undefined,
      query: undefined,
    }
  },

  async asyncData({ query }) {
    let random = Math.random()

    return {
      random,
      query: JSON.stringify(query),
    }
  },
})
</script>

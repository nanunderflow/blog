<template>
  <div class="container">
    <nuxt-content :document="article" /> 
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  async asyncData({ $content, params }) {
    const article = await $content('articles', params.slug).fetch();
    return { article };
  } 
})
</script>

<style lang="postcss">
.container {
  @apply min-h-screen flex flex-col mx-auto;
}
</style>

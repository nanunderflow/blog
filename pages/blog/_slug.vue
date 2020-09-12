<template>
  <div class="container">
    <header>
      <h1>{{ article.title }}</h1>
    </header>
    <div class="description">
      <p>
        {{ article.description }}
      </p>
    </div>
    <div class="body">
      <nuxt-content :document="article" />
    </div>
    <div class="published">
      {{ article.published }}
    </div>
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

header {
  display: flex;
  align-items: center;
  flex-direction: column;
  margin-top: 1rem;
}

h1 {
  font-weight: 300;
  font-size: 5rem;
  line-height: 1.2;
}

.description {
  display: flex;
  margin-top: 2rem;
  margin-bottom: 2rem;
  justify-content: center;
}

.description p {
  width: auto;
  max-width: 90%;
  font-weight: bolder;
  font-size: 1.8rem;
  line-height: 1.2;
}

@screen md {
  .description p {
    width: auto;
    max-width: 70%;
  }
}

.published {
  margin-bottom: 1rem;
  text-align: center;
}

.body {
  display: flex;
  flex-direction: column;
  align-content: center;
}

.body p {
  font-size: 1.6rem;
  font-weight: 500;
  line-height: 1.2;
  margin-bottom: 1rem;
}

</style>

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
  width:90%;
}

@screen md {
  .container {
    width: 80%;
  }
}

@screen lg {
  .container {
    width: 65%;
  }
}

header {
  display: flex;
  align-items: center;
  flex-direction: column;
  margin-top: 1.5rem;
}

h1 {
  font-weight: 600;
  font-size: 5rem;
  line-height: 1.2;
  color: #0e84b7;
  text-decoration: underline;
}

h2 {
  font-weight: bold;
  font-size: 1.4rem;
  line-height: 1.2;
  color: #b70e84;
  margin-bottom: 1rem;
}

.description, .published {
  display: flex;
  margin-top: 2rem;
  justify-content: center;
  font-weight: 300;
  line-height: 1.2;
}

.description {
  font-size: 1.8rem;
  margin-bottom: 2.5rem;
  color: #4a5568;
}

.published {
  font-size: 1.2rem;
  font-weight: bold;
  margin-bottom: 1.4rem;
  align-self: flex-end;
  color: #b7410e;
}

.body {
  flex-grow: 1;
}

.body p {
  font-size: 1.4rem;
  font-weight: 400;
  line-height: 1.4;
}

.body p:not(:last-child) {
  margin-bottom: 2rem;
}

.footnotes hr {
  display: none;
}

</style>

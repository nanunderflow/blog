<template>
  <div class="container">
    <div class="item">
      <img src="/me.jpg" alt="Brad Fitzwater's Picture" class="me rounded-full" />
    </div>
    <div class="item">
      <div class="bio-short">
        <p class="pb-4">
          Hi, my name is <span class="name">Brad Fitzwater</span>. 
        </p>
        <p class="pb-4">
          I am a <span class="profession">Software Engineer</span> living in Raleigh, NC.
          I was born and raised in Charleston, WV and graduated with a degree in
          <span class="degree">Computer Science</span> from Marshall University. I enjoy tinkering with web 
          things, drinking coffee and beer, reading old books, and listening noisy music.
        </p>
        <p class="pb-4">
          I am a husband and a father of twins.
        </p>
        <p class="pb-4">
          This site will, most likely, always be a work in progress. 👋
        </p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({})
</script>

<style lang="postcss">
/**
  rust b7410e
  cyan b70e84
  green 0eb741
  blue 0e84b7
*/

.container {
  @apply min-h-screen flex flex-col items-center mx-auto;
}

.item {
  @apply w-full flex justify-center;
  margin-top: 2rem;
}

.name {
  font-weight: bold;
  text-decoration: underline;
}

.profession {
  font-weight: bold;
  color: #b7410e;
}

.degree {
  font-weight: bold;
  color: #0eb741;
}

img.me {
  height: 284px;
  width: 284px;
}

.bio-short {
  padding: 1.5rem;
}

p {
  font-size: 1.2rem;
}

@screen md {
  .container {
    @apply min-h-screen flex flex-row justify-center items-center mx-auto;
  }

  .item {
    @apply w-1/2 flex justify-end;
  }

  img.me {
    margin-right: 3rem;
    height: 324px;
    width: 324px;
  }

  p {
    font-size: 1.3rem;
  }
}

@screen lg {
  img.me {
    height: 334px;
    width: 334px;
  }

  p {
    font-size: 1.4rem;
  }
}
</style>

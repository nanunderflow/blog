<template>
  <div class="container">
    <div>
      <img src="/me.jpg" alt="Brad Fitzwater's Picture" class="me" />
    </div>
    <div>
      <div>
        <p>
          👋, my name is Brad Fitzwater. I am a Software Engineer living in Raleigh, NC. 
          I was born and raised in Charleston, WV and graduated with a degree in 
          Computer Science from Marshall University. I enjoy tinkering with web things, 
          drinking coffee and beer, reading old books, and listening noisy rock albums.
        </p>
        <p>
          I am a husband and a father of twins.
        </p>
        <p>
          This site will, most likely, always be a work in progress. 🍻
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
.container {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-weight: 400;
  font-size: 1em;
  line-height: 1.2;
}

.container {
  @apply min-h-screen flex flex-col justify-center items-center mx-auto;
}

@screen md {
  .container {
    @apply min-h-screen flex flex-row justify-center items-center mx-auto;
  }
}

.container > div {
  @apply w-1/2;
  @apply flex justify-center;
}

img.me {
  @apply rounded-full;
  height: 244px;
  width: 244px;
}

@screen md {
  img.me {
    @apply rounded-full;
    height: 384px;
    width: 384px;
  }
}

p {
  @apply pb-2 pt-2;
  font-size: 1.5rem;
}
</style>

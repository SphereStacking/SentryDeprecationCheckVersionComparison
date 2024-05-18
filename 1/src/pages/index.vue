<template>
  <div>
    1
    <button @click="handleClick">
      Test Error Capture Exception
    </button>
    <button @click="addEventListenerUnload">
      Test Unload
    </button>
    <a href="/">
      Test Error Capture Exception
    </a>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  methods: {
    handleClick() {
      console.log('handleClick')
      this.$sentry.captureException(new Error('Sentry test error'));
    },
    addEventListenerUnload() {
      window.addEventListener('unload', () => {
        console.log('unload')
      })
    }
  }
}
</script>

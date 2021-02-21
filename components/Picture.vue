<template>
  <img :src="source" :alt="alternative">
</template>

<script>
export default {
  name: 'Picture',
  props: {
    source: {
      type: String,
      default: null
    },
    alternative: {
      type: String,
      default: null
    }
  }
}
</script>

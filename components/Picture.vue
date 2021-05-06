<template>
  <div class="picture">
    <img :src="source" :alt="alternative">
    <h5 class="picture_title">
      {{ title }}
    </h5>
    <div class="buttones">
      <button class="button is-small is-light">
        View
      </button>
      <a class="button is-small is-primary is-light" :href="download" target="_blank">Download</a>
    </div>
  </div>
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
    },
    title: {
      type: String,
      default: 'This image has no title yet'
    },
    download: {
      type: String,
      default: null
    }
  }
}
</script>

<style>
  .picture {
    background-color: rgba(0, 0, 0, 0.1);
    border: 12px rgba(0, 0, 0, 0) solid;
    border-radius: 10px;
  }

  .picture img {
    border-radius: 8px;
  }

  .picture .picture_title {
    width: 90%;
    height: 100%;
    line-height: 1.2;
    text-align: center;
    margin: 12px auto 0 auto;
  }

  .buttones {
    margin-top: 12px;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .buttones button {
    margin-right: 1rem !important;
  }
</style>

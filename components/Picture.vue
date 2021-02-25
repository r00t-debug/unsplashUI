<template>
  <div class="picture">
    <img :src="source" :alt="alternative">
    <div class="buttones">
      <button class="button is-small is-light">
        View
      </button>
      <a href="#" class="button is-small is-primary is-light">Download</a>
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

<template>
  <div class="section">
    <div class="columns is-multiline">
      <div v-for="picture in pictures" :key="picture.id" class="column is-3">
        <Picture :source="picture.urls.raw + '&h=720&w=1280&fit=crop'" :alternative="picture.description" :title="picture.alt_description" :download="picture.urls.raw" />
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import Picture from '../../components/Picture'
export default {
  name: 'Images',
  components: {
    Picture
  },
  data () {
    return {
      pictures: []
    }
  },
  async mounted () {
    const config = {
      headers: {
        Authorization: 'Client-ID wqwM4_7LzeesXxB3G36cwVjmPi7Zfx3IiRpsxY-JGDk'
      }
    }

    await axios
      .get('https://api.unsplash.com/photos?page=1&per_page=20', config)
      .then((res) => {
        this.pictures = res.data
      })
      .catch((err) => {
        window.console.log(err)
      })
  }
}
</script>

<style>
.section {
  padding: 6rem;
}

@media screen and (max-width: 768px) {
  .section {
    padding: 6rem 2.5rem;
  }
}
</style>

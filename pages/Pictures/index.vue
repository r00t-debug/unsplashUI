<template>
  <div class="pictures">
    <!-- <div id="sec">
      <a href="nigga_soda">nigga soda</a>
    </div> -->
    <div class="section">
      <div class="columns is-multiline">
        <div v-for="picture in pictures" :key="picture.id" class="column is-3">
          <Picture :source="picture.urls.raw + '&h=720&w=1280&fit=crop'" :alternative="picture.description" />
        </div>
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

#sec {
  display: inline-block;
  position: relative;
  padding-bottom: 3px;
}
#sec:after {
  content: '';
  display: block;
  margin: auto;
  height: 3px;
  width: 0px;
  background: transparent;
  transition: width .5s ease, background-color .5s ease;
}
#sec:hover:after {
  width: 100%;
  background: blue;
}

@media screen and (max-width: 768px) {
  .section {
    padding: 2.5rem;
  }
}
</style>

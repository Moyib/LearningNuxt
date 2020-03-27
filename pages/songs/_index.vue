<template>
  <div class="container">
    <h1>Results for: {{ $route.params.index }}</h1>
    <div v-if="albumExists">
      <div v-for="(album, index) in albumData" :key="index">
        <albumCard
          :title="album.collectionCensoredName"
          :image="album.artworkUrl100"
          :artistName="album.artistName"
          :url="album.artistViewUrl"
          :color="picker(index)"
        />
      </div>
    </div>
    <div v-else>
      <h5>Could not find artiste</h5>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import albumCard from './components/albumCard.vue'
export default {
  components: {
    albumCard
  },
  asyncData ({ params }) {
    return axios.get(`https://itunes.apple.com/search?term=${params.index}&entity=album`)
      .then((response) => {
        return { albumData: response.data.results }
      })
  },
  middleware: 'search',
  computed: {
    albumExists () {
      return this.albumData.length > 0
    }
  },
  methods: {
    picker (index) {
      return index % 2 === 0 ? 'red' : 'blue'
    }
  },
  head () {
    return {
      title: 'Your favourite songs',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Best place for your fav songs'
        }
      ]
    }
  }
}
</script>
<style scoped>
.container {
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
</style>

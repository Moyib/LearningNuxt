<template>
  <div class="container">
    <h3>Results for: {{ $route.params.index }}</h3>
    <albumCard :data="albumData" />
  </div>
</template>

<script>
import albumCard from '@/components/albumCard.vue'
export default {
  components: {
    albumCard
  },
  asyncData ({ params, app }) {
    return app.$axios.$get(`https://itunes.apple.com/search?term=${params.index}&entity=album`)
      .then((response) => {
        return { albumData: response.results }
      })
  },
  middleware: 'search',
  computed: {
    albumExists () {
      return this.albumData.length > 0
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
h3 {
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
  margin-bottom: 2rem;
  margin-top: 1rem;
  text-align: center;

}
</style>

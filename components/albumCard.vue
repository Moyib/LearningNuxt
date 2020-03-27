<template>
  <div class="row">
    <div v-for="(album, index) in data" :key="index" class="col-md-4 col-lg4">
      <a :href="album.artistViewUrl" target="_blank">
        <img
          :src="album.artworkUrl100"
          class="img-fluid"
        >
      </a>
      <h6>{{ album.collectionCensoredName }}</h6>
      <h6>{{ album.artistName }}</h6>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    data: {
      type: Array,
      default: null
    }
  }
}
</script>
<style scoped>
img {
  border-radius: 1rem;
  width: 200px;
  margin-top: 1.5rem;
}
h6 {
  margin: 0 auto;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
</style>

<template>
  <div class="row">
    <div v-for="(data, index) in products" :key="index" class="col-md-4 col-lg4">
      <img
        :href="url"
        target="_blank"
        :color="color"
        :src="image"
        height="100px"
        class="img-fluid"
      >
      <h5>{{ title }}</h5>
      <h5>{{ artistName }}</h5>
    </div>
  </div>
</template>
<script>
export default {
  props: ['title', 'image', 'artistName', 'url', 'color']
}
</script>

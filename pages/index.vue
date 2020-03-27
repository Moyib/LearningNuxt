<template>
  <div>
    <h3>Welcome to the best music app</h3>
  </div>
</template>

<script>
export default {
  head () {
    return {
      title: 'Welcome to your fav music app',
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
    text-align: center;
    margin-top: 2rem;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
  }
</style>

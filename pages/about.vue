<template>
  <div>
    <h1>About itunes music</h1>
    <p>This is an app that displays your favourite songs.</p>
    <p>Just type in your favourite artiste's name and go!</p>
  </div>
</template>

<script>
export default {
  head () {
    return {
      title: 'About Us',
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
div {
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
h1 {
  margin-top: .5rem;
  margin-bottom: 50px;
}
h1, p {
  text-align: center;
}
</style>

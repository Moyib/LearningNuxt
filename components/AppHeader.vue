<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
      <a class="navbar-brand" href="#">Bop-Bop</a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarColor01"
        aria-controls="navbarColor01"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon" />
      </button>

      <div id="navbarColor01" class="collapse navbar-collapse">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item active">
            <nuxt-link class="nav-link" to="/">
              Home
            </nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/songs">
              Music
            </nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/about">
              About
            </nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/artistes">
              Artistes
            </nuxt-link>
          </li>
        </ul>
        <form class="form-inline my-2 my-lg-0" @submit.prevent="submit">
          <input v-model="search" class="form-control mr-sm-2" type="text" placeholder="Find your fav songs" autofocus>
          <button class="btn btn-secondary my-2 my-sm-0" type="submit">
            Search
          </button>
        </form>
        <nuxt-link class="nav-link" to="/">
          <svg
            class="bi bi-arrow-clockwise"
            width="2.2em"
            height="2.2em"
            viewBox="0 0 16 16"
            fill="currentColor"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path fill-rule="evenodd" d="M3.17 6.706a5 5 0 017.103-3.16.5.5 0 10.454-.892A6 6 0 1013.455 5.5a.5.5 0 00-.91.417 5 5 0 11-9.375.789z" clip-rule="evenodd" />
            <path fill-rule="evenodd" d="M8.147.146a.5.5 0 01.707 0l2.5 2.5a.5.5 0 010 .708l-2.5 2.5a.5.5 0 11-.707-.708L10.293 3 8.147.854a.5.5 0 010-.708z" clip-rule="evenodd" />
          </svg>
        </nuxt-link>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'Appheader',
  methods: {
    submit (event) {
      this.$router.push(`songs/${this.search}`)
    }
  }
}
</script>

<style scoped>
svg {
    color: black;
    border: 1px solid transparent;
    border-radius: 1.5rem;
    background-color: whitesmoke;
    opacity: 0.5;
}
</style>

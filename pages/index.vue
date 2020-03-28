<template>
  <div>
    <h3>
      Welcome to Bop Bop <svg
        class="bi bi-music-note-beamed"
        width="1em"
        height="1em"
        viewBox="0 0 16 16"
        fill="currentColor"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path d="M6 13c0 1.105-1.12 2-2.5 2S1 14.105 1 13c0-1.104 1.12-2 2.5-2s2.5.896 2.5 2zm9-2c0 1.105-1.12 2-2.5 2s-2.5-.895-2.5-2 1.12-2 2.5-2 2.5.895 2.5 2z" />
        <path fill-rule="evenodd" d="M14 11V2h1v9h-1zM6 3v10H5V3h1z" clip-rule="evenodd" />
        <path d="M5 2.905a1 1 0 01.9-.995l8-.8a1 1 0 011.1.995V3L5 4V2.905z" />
      </svg>
    </h3>
    <h6>Here, you'll find your favourite songs</h6>
    <div class="row">
      <div v-for="(data, index) in singers" :key="index" class="col-md-4 col-lg4">
        <a target="_blank" :href="data.href">
          <img :src="data.image" class="img-fluid">
        </a>
        <h5>{{ data.singerName }}</h5>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      singers: [
        {
          singerName: 'Beyonce',
          image: require('@/assets/beyonce.jpeg'),
          href: 'https://music.apple.com/us/artist/beyonc%C3%A9/1419227?uo=4'
        },
        {
          singerName: 'Cardi B',
          image: require('@/assets/cardib.jpeg'),
          href: 'https://music.apple.com/us/artist/cardi-b/956078923?uo=4'
        },
        {
          singerName: 'Ludovico Einaudi',
          image: require('@/assets/ludovico.jpeg'),
          href: 'https://music.apple.com/us/artist/ludovico-einaudi/7420827?uo=4'
        },
        {
          singerName: 'Jacob Banks',
          image: require('@/assets/jacobbanks.jpeg'),
          href: 'https://music.apple.com/us/artist/jacob-banks/625014171?uo=4'
        },
        {
          singerName: 'John Legend',
          image: require('@/assets/johnlegend.jpeg'),
          href: 'https://music.apple.com/us/artist/john-legend/16586443?uo=4'
        },
        {
          singerName: 'Davido',
          image: require('@/assets/davido.jpeg'),
          href: 'https://music.apple.com/us/artist/davido/254654363?uo=4'
        },
        {
          singerName: 'Simi',
          image: require('@/assets/simi.jpeg'),
          href: 'https://music.apple.com/us/artist/simi/305148918?uo=4'
        },
        {
          singerName: 'Adekunle Gold',
          image: require('@/assets/adekunle.jpeg'),
          href: 'https://music.apple.com/us/artist/adekunle-gold/1035126760?uo=4'
        },
        {
          singerName: 'Wizkid',
          image: require('@/assets/wizkid.jpeg'),
          href: 'https://music.apple.com/us/artist/wizkid/309335750?uo=4'
        }
      ]
    }
  },
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
  * {
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
  }
  h3, h6 {
    text-align: center;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
  }
  h6 {
    margin-bottom: 2rem;
  }
  h3 {
    margin-top: 1rem;
  }
  .row {
    margin: 0 4rem;
  }
  img {
    margin-top: 1.5rem;
    border-radius: .5rem;
  }
</style>

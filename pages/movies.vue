<template>
  <div class="container">
    <movie v-for="movie in movies" :key="movie.id" :movie="movie" class="m-3" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import Movie from '~/components/Movie.vue'
import MovieType from '~/models/Movie'

@Component({
  components: {
    Movie
  }
})
export default class MoviePage extends Vue {
  movies: MovieType[] = []
  async created() {
    const res = await this.$axios.get('/movies')
    this.movies = res.data.results
  }
}
</script>

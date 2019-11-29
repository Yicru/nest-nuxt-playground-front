<template>
  <div class="max-w-sm w-full lg:max-w-full lg:flex">
    <img
      class="h-48 lg:h-auto lg:w-48 flex-none bg-cover rounded-t lg:rounded-t-none lg:rounded-l text-center overflow-hidden"
      :src="src(movie.poster_path)"
      alt=""
    />
    <div
      class="border-r border-b border-l border-gray-400 lg:border-l-0 lg:border-t lg:border-gray-400 bg-white rounded-b lg:rounded-b-none lg:rounded-r p-4 flex flex-col justify-between leading-normal"
    >
      <div class="mb-8">
        <p class="text-gray-600">{{ movie.release_date }}</p>
        <div class="text-gray-900 font-bold text-xl mb-2">
          {{ movie.title }}
        </div>
        <p class="text-gray-700 text-base">
          {{ movie.overview }}
        </p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator'
import MovieType from '~/models/Movie'

@Component
export default class Movie extends Vue {
  @Prop({ type: Object, required: true }) movie!: MovieType

  src(path: string): string {
    return 'https://image.tmdb.org/t/p/w500' + path
  }
}
</script>

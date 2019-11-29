<template>
  <ul class="flex border-b">
    <li class="mr-1" :class="{ '-mb-px': isCurrent('/users') }">
      <a :class="classObject('/users')" href="/users">Users</a>
    </li>
    <li class="mr-1" :class="{ '-mb-px': isCurrent('/users') }">
      <a :class="classObject('/movies')" href="/movies">Movies</a>
    </li>
  </ul>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

@Component
export default class Navigation extends Vue {
  isCurrent(currentPath: string): boolean {
    return currentPath === window.location.pathname
  }

  classObject(currentPath: string): object {
    const isCurrent = this.isCurrent(currentPath)
    return {
      'current-link': isCurrent,
      'link hover:text-blue-800': !isCurrent
    }
  }
}
</script>

<style>
.current-link {
  @apply bg-white inline-block border-l border-t border-r rounded-t py-2 px-4 text-blue-700 font-semibold;
}
.link {
  @apply bg-white inline-block py-2 px-4 text-blue-500 font-semibold;
}
</style>

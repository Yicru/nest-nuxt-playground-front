<template>
  <div class="max-w-xs rounded overflow-hidden shadow-lg my-2">
    <div class="px-6 py-4">
      <div class="font-bold text-xl mb-2">{{ user.name }}</div>
      <p class="text-grey-darker text-base">ID: {{ user.id }}</p>
      <p class="text-grey-darker text-base">AGE: {{ user.age }}</p>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator'
import UserType from '~/models/User'

@Component
export default class Profile extends Vue {
  @Prop({ type: Object, required: true }) user!: UserType
}
</script>

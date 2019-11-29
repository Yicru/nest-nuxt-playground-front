<template>
  <div class="container">
    <Profile v-for="user in users" :key="user.id" :user="user" class="m-3" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import UserType from '~/models/User'
import Profile from '~/components/Profile.vue'

@Component({
  components: {
    Profile
  }
})
export default class UserPage extends Vue {
  users: UserType[] = []
  async created() {
    const res = await this.$axios.get('/')
    this.users = res.data
  }
}
</script>

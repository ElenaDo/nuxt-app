<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <a class="navbar-brand" href="#">Nuxt SSR</a>
      <div class="collapse navbar-collapse">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item">
            <nuxt-link exact active-class="active" class="nav-link" to="/">
              Home
            </nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link active-class="active" class="nav-link" to="/about">
              About
            </nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link active-class="active" class="nav-link" to="/users">
              Users
            </nuxt-link>
          </li>
          <li v-if="!hasToken" class="nav-item">
            <nuxt-link active-class="active" class="nav-link" to="/login">
              Login
            </nuxt-link>
          </li>
          <li v-else class="nav-item">
            <a active-class="active" class="nav-link" href="#" @click.prevent="logout">
              Logout
            </a>
          </li>
        </ul>
      </div>
    </nav>
  </div>
</template>
<script>
export default {
  computed: {
    hasToken () {
      return this.$store.getters.hasToken
    }
  },
  methods: {
    logout () {
      this.$store.dispatch('logout')
      this.$router.push('/login')
    }
  }
}
</script>

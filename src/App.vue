<template>
  <div id="app">
    <base-spinner />
    <h1>Avic Food</h1>
    <router-view/>
  </div>
</template>

<script>
import BaseSpinner from './components/global/BaseSpinner'

export default {
  name: 'App',
  components: {
    BaseSpinner
  },
  data: () => ({ isLogged: false }),
  mounted () {
    this.$firebase.auth().onAuthStateChanged(user => {
      window.uid = user ? user.uid : null
      this.isLogged = !!user

      this.$router.push({ name: window.uid ? 'home' : 'login' })

      setTimeout(() => {
        this.$root.$emit('Spinner::hide')
      }, 300)
    })
  }
}
</script>
<style lang="scss">
#app {
  min-height: 100vh;
  background-color: var(--dark);
  color: var(--light);

}
</style>

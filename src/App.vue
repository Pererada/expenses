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
  mounted () {
    console.log(this.$firebase)
  },
  methods: {
    mostrarSpinner () {
      this.$root.$emit('Spinner::show')
    }
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

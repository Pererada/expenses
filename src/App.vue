<template>
  <div id="app">
    <base-spinner />
    <button @click="mostrarSpinner()">
    Vai vendo mané</button>
    <!--<router-view/>-->
  </div>
</template>

<script>
import BaseSpinner from './components/global/BaseSpinner'

export default {
  name: 'APP',
  components: {
    BaseSpinner
  },
  methods: {
    mostrarSpinner () {
      this.$root.$emit('Spinner::show')
    }
  }
}
</script>
<style lang="scss"></style>

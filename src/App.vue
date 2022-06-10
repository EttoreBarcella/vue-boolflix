<template>
  <div id="app">
    <BaseHeader/>
    <BaseMain/>
  </div>
</template>

<script>
import BaseHeader from './components/Header/BaseHeader.vue'
import BaseMain from './components/Main/BaseMain.vue'

export default {
  name: 'App',
  components: {
    BaseHeader,
    BaseMain,
  }
}
</script>

<style lang="scss">

</style>

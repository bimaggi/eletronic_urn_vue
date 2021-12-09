<template>
  <div id="app">
    <h1>VOTE COM CONSCIÊNCIA</h1>
    <app-header/>
    <ballot-box />
  </div>
</template>

<script>
import AppHeader from '@/components/AppHeader'
import BallotBox from '@/components/BallotBox'

export default {
  name: 'App',
  components: {
    AppHeader,
    BallotBox,
  },
}
</script>

<style lang="stylus">
  @import './styles/global.styl'
  #app{
    width: 100vw
    height: 100vh
    display: flex
    flex-direction: column
    justify-content: center
    align-items: center

  }
 </style>

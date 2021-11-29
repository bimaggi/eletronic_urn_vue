<template>
  <div id="app">
    <app-ballot/>
    <ballot-box />
  </div>
</template>

<script>
import AppBallot from '@/components/AppBallot'
import BallotBox from '@/components/BallotBox'

export default {
  name: 'App',
  components: {
    AppBallot,
    BallotBox,
  },
}
</script>

<style lang="stylus">
  @import './styles/global.styl'
  #app{
    background-color: black
    width: 100vw
    height: 100vh
    display: flex
    flex-direction: column
    justify-content: center
    align-items: center
  }
</style>

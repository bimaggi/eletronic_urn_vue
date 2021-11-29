<template>
  <div class="box">
    <ballot-screen/>
    <ballot-board/>
  </div>
</template>

<script>
import BallotBoard from '@/components/BallotBoard'
import BallotScreen from '@/components/BallotScreen'

export default {
  name: 'BallotBox',
  components: {
    BallotBoard,
    BallotScreen,
  },
}
</script>

<style lang="stylus" scoped>
 .box {
    width: 700px
    height: 400px
    background-color: $colorBox
    padding: 30px
    border-radius: $radius
    display: flex
    }

</style>

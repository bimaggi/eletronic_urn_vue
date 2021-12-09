<template>
  <div class="party">
    <div>Números:</div>
    <div
      v-for="(value,key) in party.padEnd(caracters,' ')"
      :key="key"
      class="party__number"
    >
      {{value}}
    </div>
  </div>
</template>
<script>
export default {
  name: 'BallotParty',
  props: {
    party: {
      type: String,
    },
    caracters: {
      type: Number,
    },
  },
}
</script>
<style lang="stylus" scoped>
.party
  display: flex
  align-items: center

.party__number
  width: 10%
  height: 45px
  border: 1px solid black
  margin: 1% 0% 3% 3%
  display: flex
  justify-content: center
  align-items: center
  font-size: 1.2rem
</style>

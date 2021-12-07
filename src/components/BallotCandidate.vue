<template>
  <div class="candidate">
    <img
      :src="require(`@/assets/images/${candidate.img}.png`)"
      class="candidate__image"
    >
  </div>
</template>
<script>
export default {
  name: 'BallotCandidate',
  props: {
    party: {
      type: String,
    },
    candidate: {
      type: String,
    },
  },
}
</script>
<style lang="stylus" scoped>
.candidate
  width: 30%
  display: flex
  flex-direction: column
  justify-content: center
  align-items: center

.candidate__image
  width: 90%
  border-radius: $radius
  margin-top: 1%
  border: 1px solid $borderDark

.candidate__name
  font-size: .6rem

.candidate__number
  @extends.candidate__name
</style>

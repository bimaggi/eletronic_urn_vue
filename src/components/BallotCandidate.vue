<template>
  <div class="candidate">
    <img
      :src="require(`@/assets/images/${candidateImage}.png`)"
      class="candidate__image"
    >
  </div>
</template>
<script>
export default {
  name: 'BallotCandidate',
  props: {
    candidateImage: {
      type: String,
    },
  },
}
</script>
<style lang="stylus" scoped>
.candidate
  width: 35%
  display: flex
  flex-direction: column
  justify-content: center
  align-items: center
  margin-top: 15%

.candidate__image
  border: 1px solid $borderDark

.candidate__name
  font-size: .6rem

.candidate__number
  @extends.candidate__name
</style>

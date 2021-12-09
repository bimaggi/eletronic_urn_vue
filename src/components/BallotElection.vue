<template>
<div class="election">
  <div class="election__title">Seu voto para:</div>
  <div> <strong>{{isVote}}</strong></div>
</div>
</template>

<script>
export default {
  name: 'BallotElection',
  props: {
    isVote: {
      type: String,
    },
  },
}
</script>

<style lang="stylus" scoped>
.election
  display: flex
  flex-direction: column

.election__title
  margin-bottom: 6%

</style>

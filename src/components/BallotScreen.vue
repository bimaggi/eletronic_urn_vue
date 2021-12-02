<template>
  <div class="screen">
      <div v-if="isVote">
        <ballot-election
          :isVote="isVote"
        />
        <ballot-party
          :party="party"
          :caracters="caracters"
        />
        <ballot-candidate/>
        <ballot-instruction/>
      </div>
      <div v-else>
        Finalização
      </div>
  </div>
</template>

<script>
import BallotElection from '@/components/BallotElection'
import BallotParty from '@/components/BallotParty'
import BallotCandidate from '@/components/BallotCandidate'
import BallotInstruction from '@/components/BallotInstruction'

export default {
  name: 'BallotScreen',
  components: {
    BallotElection,
    BallotParty,
    BallotCandidate,
    BallotInstruction,
  },
  props: {
    isVote: {
      type: String,
    },
    caracters: {
      type: Number,
    },
    party: {
      type: String,
    },
  },

}
</script>

<style lang="stylus" scoped>
.screen
  width: 50%
  background-color: $colorScrenn
  border: 1px solid $borderLight
  padding: 15px
  color: $fontDark
</style>

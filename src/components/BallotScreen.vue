<template>
  <div class="screen">
    <div v-if="isVote">
      <div class="screen_candidate">
        <ballot-election
          :isVote="isVote"
        />
        <ballot-candidate
          :party="party"
          :candidate="candidate"
        />
      </div>
      <ballot-party
        :party="party"
        :caracters="caracters"
      />
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
    candidate: {
      type: String,
    },
  },

}
</script>

<style lang="stylus" scoped>
.screen
  width: 52%
  background-color: $colorScrenn
  border: 1px solid $borderLight
  padding: 15px
  color: $fontDark

.screen_candidate
  width: 100%
  height: 60px
  display: flex
  justify-content: space-between
</style>

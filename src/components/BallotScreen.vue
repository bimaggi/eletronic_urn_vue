<template>
  <div class="screen">
    <div v-if="isVote">
      <div class="screen_candidate">
        <ballot-election
          :isVote="isVote"
        />
        <ballot-candidate
          :candidate-image="candidate.img"
          :key="candidate.img"
        />
      </div>
      <ballot-party
        :party="party"
        :caracters="caracters"
      />
      <ballot-description
        :party="party"
        :candidate="candidate"
      />
      <ballot-instruction/>
      </div>
      <div v-else>
        <ballot-finished/>
      </div>
  </div>
</template>

<script>
import BallotElection from '@/components/BallotElection'
import BallotParty from '@/components/BallotParty'
import BallotCandidate from '@/components/BallotCandidate'
import BallotInstruction from '@/components/BallotInstruction'
import BallotDescription from '@/components/BallotDescription'
import BallotFinished from '@/components/BallotFinished'

export default {
  name: 'BallotScreen',
  components: {
    BallotElection,
    BallotParty,
    BallotCandidate,
    BallotInstruction,
    BallotDescription,
    BallotFinished,
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
      type: Object,
    },
  },

}
</script>

<style lang="stylus" scoped>
.screen
  width: 58%
  background-color: $colorScrenn
  border: 1px solid $borderLight
  padding: 15px
  color: $fontDark
  font-size: .9rem

.screen_candidate
  width: 100%
  height: 60px
  display: flex
  justify-content: space-between
</style>

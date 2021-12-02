<template>
  <div class="box">
    <ballot-screen
      :isVote="isVote"
      :party="party"
      :caracters="caracters"
      />
    <ballot-board
      :setParty="setParty"
    />
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
  data() {
    return {
      isVote: 'Prefeito',
      party: '',
      caracters: 2,
      candidate: {},
      candidates: {
        prefeitos: {
          11: {
            name: 'Marcia',
            party: 14,
            image: '@/assets/images/hashirama.jpeg',
          },
          14: {
            name: 'José',
            party: 20,
            image: '',
          },
        },
        vereadores: {
          2543: {
            name: 'Juanita',
            party: 14,
            image: '',
          },
          54467: {
            name: 'Joselito',
            party: 20,
            image: '',
          },
        },
      },
    }
  },
  methods: {
    setParty(value) {
      if (this.party.length === this.caracters) {
        return false
      }
      this.party += `${value}`
      return this.validateCandidate()
    },
    validateCandidate() {
      if (this.party.length < this.caracters) {
        return false
      }
      if (this.candidates[this.isVote][this.party]) {
        this.candidate = this.candidates[this.isVote][this.party]
        return true
      }
      this.candidate = {
        name: 'Voto Nulo',
        party: 'Voto Nulo',
        imagem: ' ',
      }
      return true
    },
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
    justify-content: space-between
    }

</style>

<template>
  <div class="box">
    <ballot-screen
      :isVote="isVote"
      :party="party"
      :caracters="caracters"
      :candidate="candidate"
    />
    <ballot-board
      @clickNumber="setParty"
      @white='votarNulo'
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
      isVote: 'Melhor Hokage',
      party: '',
      caracters: 2,
      candidate: {},
      candidates: {
        '01': {
          img: 'hashirama',
          name: 'Senju, Hashirama',
        },
        '02': {
          img: 'tobirama',
          name: 'Senju, Tobirama',
        },
        '03': {
          img: 'hiruzen',
          name: 'Sarutobi, Hiruzen',
        },
        '04': {
          img: 'minato',
          name: 'Namikaze, Minato',
        },
        '05': {
          img: 'tsunade',
          name: 'Senju, Tsunade',
        },
        '06': {
          img: 'kakashi',
          name: 'Hatake, Kakashi',
        },
        '07': {
          img: 'naruto',
          name: 'Uzumaki, Naruto',
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
      if (this.candidates[this.party]) {
        this.candidate = this.candidates[this.party]
        return true
      }
      this.candidate = {
        name: 'Voto Nulo',
        party: 'Voto Nulo',
        imagem: ' ',
      }
      return true
    },
    votarNulo() {
      console.log(this.candidate.name)
      console.log('to fazendo teste')

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

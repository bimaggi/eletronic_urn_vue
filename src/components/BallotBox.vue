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
      @white='whiteVote'
      @delete='deleteVote'
      @confirm='confirmVote'
    />
  </div>
</template>

<script>
import BallotBoard from '@/components/BallotBoard'
import BallotScreen from '@/components/BallotScreen'
import confirmAudio from '@/assets/audio/confirm.wav'
import keyAudio from '@/assets/audio/key.wav'
import candidates from '@/enums/candidates'

const {
  CANDIDATE1,
  CANDIDATE2,
  CANDIDATE3,
  CANDIDATE4,
  CANDIDATE5,
  CANDIDATE6,
  CANDIDATE7,
} = candidates

export default {
  name: 'BallotBox',
  components: {
    BallotBoard,
    BallotScreen,
  },
  data() {
    return {
      isVote: 'MELHOR HOKAGE',
      party: '',
      caracters: 2,
      candidate: {},
      candidates: {
        '01': {
          img: CANDIDATE1.IMG,
          name: CANDIDATE1.NAME,
        },
        '02': {
          img: CANDIDATE2.IMG,
          name: CANDIDATE2.NAME,
        },
        '03': {
          img: CANDIDATE3.IMG,
          name: CANDIDATE3.NAME,
        },
        '04': {
          img: CANDIDATE4.IMG,
          name: CANDIDATE4.NAME,
        },
        '05': {
          img: CANDIDATE5.IMG,
          name: CANDIDATE5.NAME,
        },
        '06': {
          img: CANDIDATE6.IMG,
          name: CANDIDATE6.NAME,
        },
        '07': {
          img: CANDIDATE7.IMG,
          name: CANDIDATE7.NAME,
        },
      },
    }
  },
  methods: {
    setParty(value) {
      this.playAudio(keyAudio)
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
        img: '',
      }
      return true
    },
    whiteVote() {
      if (this.isVote === false) return false
      this.clearVote()
      return this.nextScreen()
    },
    deleteVote() {
      this.clearVote()
    },
    confirmVote() {
      if (this.party.length < this.caracters) {
        return false
      }
      return this.nextScreen()
    },
    clearVote() {
      this.candidate = {
        name: '',
        img: '',
      }
      this.party = ''
    },
    nextScreen() {
      this.playAudio(confirmAudio)
      this.isVote = false
      const begin = this
      setTimeout(() => {
        begin.isVote = 'MELHOR HOKAGE'
        this.clearVote()
      }, 3000)
    },
    playAudio(value) {
      if (value) {
        const audio = new Audio(value)
        audio.play()
      }
    },
  },
}
</script>

<style lang="stylus" scoped>
 .box {
    width: 700px
    height: 390px
    background-color: $colorBox
    padding: 25px
    border-radius: $radius
    display: flex
    justify-content: space-between
  }

</style>

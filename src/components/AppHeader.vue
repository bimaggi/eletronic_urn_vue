<template>
  <div class="list">
    <div
      v-for="hokage in hokages"
      :key="hokage"
      class="list__candidate"
    >
      {{hokage.img}} - {{hokage.num}}
      <img :src="require(`@/assets/images/${hokage.img}.png`)" class="list__img">
    </div>
  </div>
</template>
<script>
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
  name: 'AppHeader',
  data() {
    return {
      hokages: [
        {
          name: CANDIDATE1.NAME,
          num: CANDIDATE1.NUM,
          img: CANDIDATE1.IMG,
        },
        {
          name: CANDIDATE2.NAME,
          num: CANDIDATE2.NUM,
          img: CANDIDATE2.IMG,
        },
        {
          name: CANDIDATE3.NAME,
          num: CANDIDATE3.NUM,
          img: CANDIDATE3.IMG,
        },
        {
          name: CANDIDATE4.NAME,
          num: CANDIDATE4.NUM,
          img: CANDIDATE4.IMG,
        },
        {
          name: CANDIDATE5.NAME,
          num: CANDIDATE5.NUM,
          img: CANDIDATE5.IMG,
        },
        {
          name: CANDIDATE6.NAME,
          num: CANDIDATE6.NUM,
          img: CANDIDATE6.IMG,
        },
        {
          name: CANDIDATE7.NAME,
          num: CANDIDATE7.NUM,
          img: CANDIDATE7.IMG,
        },
      ],
    }
  },
}
</script>
<style lang="stylus">
.list
  display: flex
  width: 100%
  color: $fontLight
  justify-content: center

.list__candidate
  display: flex
  flex-direction: column
  margin: 2%
  font-size: .8rem

.list__img
  width: 90px
  border-radius: 50%
</style>

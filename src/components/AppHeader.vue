<template>
  <div class="list">
    <div
      v-for="hokage in hokages"
      :key="hokage"
      class="list__candidate"
    >
      {{hokage.name}} - {{hokage.num}}
      <img :src="require(`@/assets/images/${hokage.img}.png`)" class="list__img">
    </div>
  </div>
</template>
<script>
export default {
  name: 'AppHeader',
  data() {
    return {
      hokages: [
        {
          name: 'Hashirama',
          num: '01',
          img: 'hashirama',
        },
        {
          name: 'Tobirama',
          num: '02',
          img: 'tobirama',
        },
        {
          name: 'Hiruzen',
          num: '03',
          img: 'hiruzen',
        },
        {
          name: 'Minato',
          num: '04',
          img: 'minato',
        },
        {
          name: 'Tsunade',
          num: '05',
          img: 'tsunade',
        },
        {
          name: 'Kakashi',
          num: '06',
          img: 'kakashi',
        },
        {
          name: 'Naruto',
          num: '07',
          img: 'naruto',
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
  justify-content: center
  color: $fontLight

.list__candidate
  display: flex
  flex-direction: column
  margin: 2%
  font-size: .8rem

.list__img
  width: 85px
  border-radius: 50%
</style>

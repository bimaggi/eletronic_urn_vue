<template>
<div class="board">
  <div class="board__form">
    <div class="form__button">
      <button
        v-for="(num, key) in row1"
        :key= "key"
        class="button"

      >
        {{num}}
      </button>
    </div>
    <div class="form__button">
      <button
        v-for="(num, key) in row2"
        :key= "key"
        class="button"
      >
      {{num}}
      </button>
    </div>
    <div class="form__button">
      <button
        v-for="(num, key) in row3"
        :key= "key"
        class="button"
      >
        {{num}}
      </button>
    </div>
    <div class="form__button">
      <button
        v-for="(num, key) in row4"
        :key= "key"
        class="button"
      >
        {{num}}
      </button>
    </div>
  </div>
  <div class="button__special">
    <button class="white"> Branco</button>
    <button class="delete"> Corrige</button>
    <button class="confirm"> Confirma</button>
  </div>
</div>
</template>

<script>
export default {
  name: 'BallotBoard',
  data() {
    return {
      row1: '123',
      row2: '456',
      row3: '789',
      row4: '0',
    }
  },
}
</script>
<style lang="stylus" scoped>
.board
  width: 45%
  background-color: $colorBoard
  display: flex
  flex-direction: column
  align-items: center
  padding-top: 5%
  border-radius: $radius

.board__form
  display: flex
  flex-direction: column
  justify-content: space-around
  width: 95%
  height: 60%
  font-size: 1.6rem

.form__button
  display: flex
  justify-content: space-around
  width: 100%
  margin-top: 4%

.button
  width: 20%
  border-radius: $radius
  background-color: $colorButton
  color: $fontLight
  border: 1px solid $borderDark
  cursor: pointer

.button__special
  margin-top: 15%
  width: 95%
  height: 15%
  display: flex
  justify-content: space-between

.white
  styleButton()
  colorButton($colorWhite)

.delete
  styleButton()
  colorButton($colorDelete)

.confirm
  styleButton()
  colorButton($colorConfirm)

</style>

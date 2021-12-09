<template>
<div class="board">
  <div class="board__form">
    <div
      class="form__button"
      v-for="row in rows"
      :key="row"
    >
      <button
        v-for="(num) in row"
        :key="num"
        class="button"
        @click="$emit('clickNumber',num)"
      >
        {{num}}
      </button>
    </div>
  </div>
  <div class="button__special">
    <button
      v-for="button in buttons"
      :key="button.label"
      :class="button.class"
      @click="$emit(button.method)"
      >
      {{button.label}}
      </button>
  </div>
  </div>
</template>

<script>
export default {
  name: 'BallotBoard',
  data() {
    return {
      rows: [
        '123',
        '456',
        '789',
        '0',
      ],
      buttons: [
        {
          label: 'BRANCO',
          class: 'white',
          method: 'white',
        },
        {
          label: 'CORRIGE',
          class: 'delete',
          method: 'delete',
        },
        {
          label: 'CONFIRMA',
          class: 'confirm',
          method: 'confirm',

        },
      ],
    }
  },
}
</script>
<style lang="stylus" scoped>
.board
  width: 40%
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

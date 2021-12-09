<template>
  <div class="instruction">
    <hr/>
   <div class="instruction__title"><strong>Aperte a tecla:</strong></div>
   <p>BRANCO para VOTAR EM BRANCO</p>
   <p>LARANJA para CORRIGIR</p>
   <p>VERDE para CONFIRMAR</p>
  </div>
</template>
<script>
export default {
  name: 'BallotInstruction',
}
</script>
<style lang="stylus">
.instruction
  margin-top: 8%

.instruction__title
  margin-bottom: 5px
 p
  font-size .8rem
  padding: 1px

</style>

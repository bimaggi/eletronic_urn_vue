<template>
  <div class="description">
    <div class="description__name">
      Nome:
      <strong>
        {{candidate.name ? candidate.name : '_______________'}}
        </strong>
      </div>
    <div>Numero: <strong>{{party ? party : '_____________'}}</strong></div>
  </div>
</template>

<script>
export default {
  name: 'Description',
  props: {
    candidate: {
      type: String,
    },
    party: {
      type: String,
    },
  },
}
</script>
<style lang="stylus">
.description
  display: flex
  flex-direction: column
.description__name
  margin-bottom: 10px
  margin-top: 5px
</style>

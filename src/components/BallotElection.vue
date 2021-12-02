<template>
<div>
  <div>Seu voto para:</div>
  <div>{{isVote}}</div>
</div>
</template>

<script>
export default {
  name: 'BallotElection',
  props: {
    isVote: {
      type: String,
    },
  },
}
</script>

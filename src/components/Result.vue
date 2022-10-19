<template>
  <p>Result : {{ score }}</p>
  
  <div v-if="score < 250">
    <p>You are So fast !</p>
  </div>
  <div v-else-if="score>250 && score < 400">
    <p>You are normal</p>
  </div>
  <div v-else>
    <p>You are too slow ! Try Again.</p>
  </div>
</template>

<script>
export default {
    props:['score']
}
</script>

<style>

</style>
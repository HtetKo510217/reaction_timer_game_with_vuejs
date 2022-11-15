<template>
  <div>
   <div class="result"> Result is {{score}} ms</div>
   <p v-if="score < 250" class="success">
        Your are too fast !!!.
   </p>
   <p v-else-if="score > 250 && score < 600 " class="success">
        Your are normal !!!.
   </p>
   <p v-else class="fail">
        Your are too slow . Try again !!!!.
   </p>
  </div>
</template>

<script>
export default {
    props: ['score'],
}
</script>

<style scoped>
    .result {
        font-size: 30px;
        padding: 10px 0 30px;
    }
    p {
        width: 400px;
        margin: 0 auto;
        font-size: 25px;
        padding: 10px;
        box-shadow: 1px 1px 8px 2px darkred;

    }
    .success {
        color:darkgreen;
    }

    .fail {
        color:darkred;
    }

</style>
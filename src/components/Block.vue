<template>
  <div v-if="showBlock" class="block" @click="stopTimer">
    I am block
    <p>score  is {{score}}</p>
    <p> delay is{{delay}}</p>
  </div>
</template>

<script>
export default {
    props: [
        'delay'
    ],
    data() {
        return {
            showBlock :false,
            score : 0,
            timer: null,
        }
    },
    mounted() {
        setTimeout(()=> {
        this.showBlock = true;
        this.startTimer();
        },this.delay);
    },
    methods : {
        stopTimer () {
            clearInterval(this.timer);
            this.$emit('endGame',this.score);
        },
        startTimer() {
            this.timer=setInterval(()=> {
                this.score += 50;
            },50);
            console.log('start timer');
        }
    }
}
</script>

<style>
.block {
    width : 300px;
    height: 300px;
    box-sizing: border-box;
    background: darkred;
    color: #fff;
    padding: 10px;
    margin: 10px auto;
}
</style>
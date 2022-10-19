<template>
  <div class="block" v-if="ShowBlock" @click="stopTimer">
    Click Here {{ delay }}
  </div>
</template>

<script>
export default {
  props:['delay'],
  data(){
    return{
      ShowBlock:false,
      score:0,
      timer:null
    }
  },
  mounted(){
    setTimeout(()=>{
      this.ShowBlock = true
      this.startTimer()
    },this.delay)
  },
  methods:{
    startTimer()
    {
      this.timer = setInterval(() => {
        this.score +=50;
      }, 50);
    },
    stopTimer()
    {
      clearInterval(this.timer)
      this.$emit('endGame',this.score)
    }
  }
 
  
}
</script>

<style>
.block
{
    width: 300px;
    height: 300px;
    padding-top: 20px;
    margin: 20px auto;
    background-color: blanchedalmond;
}
</style>
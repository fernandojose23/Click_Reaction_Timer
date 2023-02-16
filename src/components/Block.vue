<template>
  <div>
      <div v-if="showBlock" @click="stopTimer" class="mt-3 max-w-sm p-6 bg-white border border-gray-200 rounded-lg shadow hover:bg-gray-100 dark:bg-gray-800 dark:border-gray-700 dark:hover:bg-gray-700">
          <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Catch Me!</h5>
      </div>
  </div>
</template>

<script>
export default {
  props:[ 'delay' ],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0,
    }
  },
  mounted() {
    console.log('mounted')
    setTimeout(() =>{
      this.showBlock = true
      this.startTimer()
    }, this.delay)
  },
  methods: {
    startTimer(){
      this.timer = setInterval(()=>{
        this.reactionTime += 10
      }, 10)
    },
    stopTimer(){
      clearInterval(this.timer)
      // console.log(this.reactionTime)
      this.$emit('end', this.reactionTime)
    }
  }
}
</script>

<style scoped>
</style>
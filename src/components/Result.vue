<template>
    <div>
        <p>Your Reaction Time is {{ score }} millisecond</p>
        <!-- <slot name="display"></slot> -->
        <p class="text-4xl font-semibold text-teal-600 dark:text-white">{{ rank }}</p>
    </div>
</template>
<script>
export default {
    props: [ 'score' ],
    data(){
        return{
            rank: null,
        }
    },
    mounted(){
        if(this.score < 250 ){
            this.rank = 'Ninja Fingers!'
        }else if(this.score < 400){
            this.rank = 'Rapid Reflexes'
        }else{
            this.rank = 'Snail Pecs...'
        }
    }
}
</script>
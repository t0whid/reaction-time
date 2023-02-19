<template>
    <div>
        <p> Reaction Time: {{ count }} ms</p>
        <p class="rank">{{ rank }}</p>
    </div>
</template>

<script>
    export default {
        props:["count"],
        data() {
            return {
                rank:null
            }
        },
        mounted() {
            if(this.score < 250) {
                this.rank = 'Very Fast'
            }
            else if(this.score < 450) {
                this.rank = 'Fast'
            }
            else if(this.score < 650) {
                this.rank = 'Medium Fast'
            }
            else if(this.score < 850) {
                this.rank = 'Slowly Clicked'
            }
            else {
                this.rank = 'Very Slowly Clicked'
            }
        }
    }
</script>

<style>
    .rank {
        color: green;
        font-size: 28px;
        padding: 20px
    }
</style>
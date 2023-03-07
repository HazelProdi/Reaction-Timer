<template>
    <div class="blockResult">
       <h5>Reaction Time:  
            <span v-if="score <= 0">0</span> 
            <span v-else>{{ score }}</span>
            ms
        </h5>
        <p class="rank">Rank : {{ rank }}</p> 
    </div>
</template>

<script>
export default {
    //props
    props: ['score'],
    data() {
        return {
            rank: null,
        }
    },
    mounted() {
        if ( this.score < 250 ){
            this.rank - 'Ninja Fingers'
        } else if (this.score < 400) {
            this.rank = 'Rapid Reflexes'
        } else {
            this.rank = 'Snail pace...'
        }
    }
}
</script>

<style>
    .rank{
        font-size: 1.4em;
        color: black;
        font-weight: bold;
    }
    .blockResult {
        width: 400px;
        border-radius: 20px;
        background: coral;
        color: black;
        text-align: center;
        padding: 100px 0;
        margin: 40px auto;
    }
</style>
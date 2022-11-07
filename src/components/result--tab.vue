<template>
    <div>
       Score is: {{score}}
       <p>{{rank}}</p>
    </div>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: ''
                }
         },
    mounted() {
        if (this.score <2500) {
            this.rank = 'Very fast'
        } else if (this.score <400)
        {
            this.rank = 'Fast'
        } else this.rank = 'slowly'
    },
}
</script>

<style>
div {
    font: 500;
    margin-top: 30px;
}
p {
    font: 400;
    font-size: 30px;
    color: blueviolet;
}
</style>
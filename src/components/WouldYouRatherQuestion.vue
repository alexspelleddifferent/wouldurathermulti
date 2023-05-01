<template>
    <div class="wyr">
        <h2>Would you rather...</h2>
        <h3>{{ question.q }}</h3>
        <input type="radio" v-model="choice" v-bind:value="question.a1" v-on:change="choiceMade"><label>{{ question.a1 }}</label>
        <input type="radio" v-model="choice" v-bind:value="question.a2" v-on:change="choiceMade"><label>{{ question.a2 }}</label>
    </div>    
</template>

<script>
export default {
    name:'QuestionBox',
    emits: ['choice-made'],
    props: {
        question: Object
    },
    data() {
        return {
            choice:''
        }
    },
    methods: {
        choiceMade() {
            this.$emit('choice-made', this.question.id, this.choice)
        }
    }
}
</script>
<style scoped>
h3 {
  margin: 40px 0 0;
}
.wyr {
  background: chartreuse
}
</style>
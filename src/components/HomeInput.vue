<template>
    <div class="homeInput">
        <h2>{{title}}</h2>
        <hr>
        <div>
            <div v-for="(answer, index) in answers" :key="index">
                <input :type="type" 
                        v-bind:name="type"
                        :value="answer"
                        :id="type + index"
                        @input="handleAnswers(e, index)"
                />
                <label :for="type + index">{{answers[index]}}</label>
            </div>
        </div>
        <hr>
        <button class="btn btn-success" @click="handleClick">Next</button>
    </div>
</template>

<script>
export default {
    props: ['type', 'title', 'answers'],
    data() {
        return {
            result: []
        }
    },
    created() {
        for (let i = 0; i < this.answers.length; i++) {
            this.result.push("false");
        }
    },
    methods: {
        handleAnswers(e, index) {
            console.log(e.target.value);
            console.log(this.result);
        },
        handleClick(e) {
            console.log(e);

            this.$emit('changedata', {

            })
        }
    },
    computed: {

    }
}
</script>
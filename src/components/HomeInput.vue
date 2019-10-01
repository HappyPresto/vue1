<template>
    <div class="homeInput">
        <h2>{{title}}</h2>
        <hr>
        <div>
            <div v-for="(answer, index) in answers" :key="index">
                <input :type="type" 
                        v-bind:name="type"
                        :value="result[index]"
                        :id="type + index"
                        @input="handleAnswers($event, index)"
                />
                <label :for="type + index">{{answers[index]}}</label>
            </div>
        </div>
        <hr>
        <button class="btn btn-success" 
                @click="handleClick"   
        >
        Next
        </button>
    </div>
</template>

<script>
export default {
    props: ['info'],
    data() {
        return {
            id: this.info.id,
            type: this.info.type,
            title: this.info.title,
            answers: this.info.answers,
            result: [],
        }
    },
    created() {
        for (let i = 0; i < this.answers.length; i++) {
            this.result.push(false);
        }
    },
    methods: {
        handleAnswers(e, index) {
            if (e.target.checked == true) {
                this.result[index] =  true;
            }
            else {
                this.result[index] =  false;
            }
        },
        handleClick(e) {
            this.$emit('changedata', {
                value: this.result
            });
        }
    },
    computed: {

    }
}
</script>
<template>
    <div class="content">
            <home-input v-for="(item, index) in info" :key="index"
                        v-if = "show +1 == item.id"
                        :info = item
                        @changedata="addToResult($event, index)"
            >
            </home-input>
            <home-result v-if="show == info.length"
                        :info = info 
                        :show = show
            >
            </home-result>
    </div>
</template>

<script>
import HomeInput from './components/HomeInput';
import HomeResult from './components/HomeResult';

export default {
    data() {
        return {
            info: [
                {
                    type: 'radio',
                    title: 'Какой тег задает ссылку?',
                    answers: [
                        'a',
                        'div',
                        'span',
                        'img'
                    ],
                    result: [],
                    id: 1
                },
                {
                    type: 'checkbox',
                    title: 'Какие из этих тегов строчные?',
                    answers: [
                        'a',
                        'div',
                        'span',
                        'img'
                    ],
                    result: [], 
                    id:2 
                }
            ],
            show: 0,
        }
    },
    methods: {
        addToResult(res, index) {
            this.info[index].result = res;
            this.show++;
        }
    },
    components: {
        HomeInput,
        HomeResult
    }
}
</script>

<style scoped>
.content {
    max-width: 600px;
    width: 100%;
    margin: 0 auto;
}
</style>
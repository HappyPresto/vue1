<template>
    <div class="content">
        <home-input v-for="(item, index) in info" :key="index"
                    :type = item.type
                    :title = item.title
                    :answers = item.answers
        >
        </home-input>

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
                    result: []
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
                    result: []
                }
            ],
        }
    },
    components: {
        HomeInput
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
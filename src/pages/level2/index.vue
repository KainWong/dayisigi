<template>
<div>
    <div class="question">{{question}}</div>
    <div class="choose-item" v-for="(item,index) in chooseList" :key="index">{{item}}</div>
</div>
</template>
<style>
</style>
<script>
    export default {
        name: 'level2',
        components: {
        },
        props: {},
        data() {
            return {
                question: '',
                chooseList: [
                    'A.',
                    'B.',
                    'C.'
                ]
            }
        },
        computed: {
        },
        watch: {
        },
        methods: {
        },
        created() {
        },
        destroyed() {
        },
        mounted() {
        }
    }
</script>
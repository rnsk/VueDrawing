<template>
    <div>
        <p><a href="https://jsonplaceholder.typicode.com/comments">検索先</a></p>
        PostID: <input placeholder="検索" name="q" type="text" v-model="q" @input="onInput">
    </div>
</template>

<script>
import axios from 'axios';

export default {
    props: {
        url: String,
    },
    data() {
        return {
            q: ''
        }
    },
    methods: {
        async onInput() {
            this.$emit('loadStart')// イベント発火
            const { data } = await axios.get(this.url + '?postId=' + this.q);
            this.$emit('loadResults', { results: data })// イベント発火
        }
    }
}
</script>

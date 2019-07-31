<template>
    <div class="box">
        <h2>Upload multiple files</h2>
    </div>
</template>

<script>
export default {
    name: 'MultipleFiles',
    props: {
        acceptType: {
            type: String,
            default: 'image/*'
        },
        uploadFieldName: {
            type: String,
            default: 'photo'
        }
    },
    data() {
        return {
            fileUrl: '',
            file: null,
            warningText: ''
        }
    },
    computed: {
        isSelected() {
            return !!this.file;
        }
    },
    mounted() {
      this.reset();
    },
    methods: {
        reset() {
            this.fileUrl = ''
            this.file = null
            this.warningText = ''
        }
    }
}
</script>

<style scoped>

</style>

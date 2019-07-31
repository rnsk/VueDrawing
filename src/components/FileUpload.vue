<template>
    <div class="file-upload">
        <h3>File Upload</h3>
        <div
          :class="{'hover-style': !isSelected}"
          class="dropbox">
            <input
                v-if="!isSelected"
                :name="uploadFieldName"
                :accept="acceptType"
                @change="onFileChange($event.target);"
                type="file"
                class="input-file">

            <p v-if="!isSelected">
                Drag your file here to begin<br> or click to browse
            </p>
            <div v-else>
                <div class="preview">
                    <img
                      v-if="fileUrl"
                      :src="fileUrl"
                      alt="preview">
                </div>
                <div class="buttons">
                    <a
                      class="button"
                      @click="reset">cancel
                    </a>
                </div>
            </div>
            <p v-if="warningText">
                {{warningText}}
            </p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'FileUpload',
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
        },
        onFileChange({name, files}) {
            if (!files.length) return;

            this.file = files[0];
            this.readUrl();
        },
        readUrl() {
            const reader = new FileReader();
            reader.onload = (event) => {
                this.fileUrl = event.target.result;
            };
            reader.readAsDataURL(this.file);
        }
    }
}
</script>

<style scoped>
  .dropbox {
    background-color: #efefef;
    cursor: pointer;
    color: #666;
    min-height: 300px;
    outline: 2px dashed #666;
    outline-offset: -10px;
    padding: 10px;
    position: relative;
  }

  .hover-style:hover {
    background-color: #ddd;
  }

  .input-file {
    cursor: pointer;
    height: 300px;
    opacity: 0;
    position: absolute;
    width: 100%;
  }

  .dropbox p {
    font-size: 1.2em;
    text-align: center;
    padding: 50px 0;
  }

  .preview {
    margin: 0 auto;
    padding: 30px 0 0;
  }

  .preview img {
    height: auto;
    max-width: 250px;
  }
</style>

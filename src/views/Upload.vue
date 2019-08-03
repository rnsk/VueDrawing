<template>
  <div class="upload">
    <FileUpload />
    <MultipleFiles />
  </div>
</template>

<script>
import FileUpload from '@/components/FileUpload.vue'
import MultipleFiles from '@/components/MultipleFiles.vue'

export default {
    name: 'upload',
    components: {
      FileUpload,
      MultipleFiles
    }
}
</script>

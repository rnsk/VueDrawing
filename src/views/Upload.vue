<template>
  <div class="upload">
    <SingleFile />
    <MultipleFiles />
  </div>
</template>

<script>
import SingleFile from '@/components/SingleFile.vue'
import MultipleFiles from '@/components/MultipleFiles.vue'

export default {
    name: 'upload',
    components: {
      SingleFile,
      MultipleFiles
    }
}
</script>

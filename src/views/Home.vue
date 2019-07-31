<template>
  <div class="home">
    <form>
      <FileUpload />
    </form>
  </div>
</template>

<script>
// @ is an alias to /src
import FileUpload from '@/components/FileUpload.vue'

export default {
  name: 'home',
  components: {
    FileUpload
  }
}
</script>

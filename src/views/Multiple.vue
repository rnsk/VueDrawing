<template>
  <div class="multiple">
    <form>
      <MultipleFiles />
    </form>
  </div>
</template>

<script>
import MultipleFiles from '@/components/MultipleFiles.vue'

export default {
    name: 'Multiple',
    components: {
        MultipleFiles
    }
}
</script>

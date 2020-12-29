<template>
  <div>
    <div v-html="md">

    </div>
  </div>
</template>

<script>
import demo from './Markdownit.md'

console.log(demo)

export default {
  data () {
    return {
      md: demo
    }
  }
}
</script>

<style  scoped>
</style>

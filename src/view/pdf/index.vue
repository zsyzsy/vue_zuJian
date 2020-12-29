<template>
  <div class="zy_content_box">
    <div class="zy_content_box_left">
      <div class="zy_content_box_left_title">pdf预览</div>
      <div class="zy_content_box_left_yl">
        <div v-for="page in numPages" :key="page" style="display: block;width: 100%;">
          <img :id="'item_'+page" class="pdf-item" src="">
        </div>
      </div>
    </div>
    <div class="zy_content_box_right">
      <!-- <div class="zy_content_box_right_showBtn">
        <el-button type="primary" round>复制</el-button>
      </div> -->
      <div class="zy_content_box_dm" v-html="md">

      </div>
    </div>
  </div>
</template>

<script>
import demo from './index.md'
export default {
  data () {
    return {
      md: demo,
      scale: 0.5,
      numPages: 0
    }
  },
  mounted () {

  },
  methods: {
  }
}
</script>
<style  scoped>
</style>

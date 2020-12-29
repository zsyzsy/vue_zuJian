<template>
  <!-- <vue-seamless-scroll :data="listData" class="seamless-warp">
        <ul class="item">
            <li v-for="item in listData">
                <span class="title" v-text="item.title"></span>
                <span class="date" v-text="item.date"></span>
            </li>
        </ul>
    </vue-seamless-scroll> -->
  <div class="zy_content_box">
    <div class="zy_content_box_left">
      <div class="zy_content_box_left_title">pdf预览</div>
      <div class="zy_content_box_left_yl">

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
      md: demo

    }
  }
}
</script>
<style  scoped>
</style>

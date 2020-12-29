<template>
  <div>
    <div class="zy_content_info">
      <pre>npm install vue-seamless-scroll --save</pre>
      然后在main.js文件里面引入使用：
      <pre>
        import scroll from 'vue-seamless-scroll'
        Vue.use(scroll)
      </pre>
    </div>
    <div class="zy_content_box">
      <div class="zy_content_box_left">
        <div class="zy_content_box_left_title">向上滚动</div>
        <div class="zy_content_box_left_yl">
          <vue-seamless-scroll :data="listData" class="seamless-warp">
            <ul class="item">
              <li v-for="item in listData">
                <span class="title" v-text="item.title"></span>
                <span class="date" v-text="item.date"></span>
              </li>
            </ul>
          </vue-seamless-scroll>
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
    <!-- 向下 -->
    <div class="zy_content_box">
      <div class="zy_content_box_left">
        <div class="zy_content_box_left_title">向下滚动设置direction: 0</div>
        <div class="zy_content_box_left_yl">
          <vue-seamless-scroll :data="listData" :class-option="classOption" class="seamless-warp">
            <ul class="item">
              <li v-for="item in listData">
                <span class="title" v-text="item.title"></span><span class="date" v-text="item.date"></span>
              </li>
            </ul>
          </vue-seamless-scroll>
        </div>
      </div>
      <div class="zy_content_box_right">
        <div class="zy_content_box_dm" v-html="downRoll">

        </div>
      </div>
    </div>
    <!-- 向左 -->
    <div class="zy_content_box">
      <div class="zy_content_box_left">
        <div class="zy_content_box_left_title">
          向左滚动 direction:2  limitMoveNum: 2
          向右滚动 direction:3  limitMoveNum: 2
          </div>
        <div class="zy_content_box_left_yl">
          <vue-seamless-scroll :data="listData" :class-option="optionLeft" class="seamless-warp2">
            <ul class="item">
              <li v-for="item in listData" v-text="item.title"></li>
            </ul>
          </vue-seamless-scroll>
        </div>
      </div>
      <div class="zy_content_box_right">
        <div class="zy_content_box_dm" v-html="leftRoll">

        </div>
      </div>
    </div>
    <!-- 向右 -->
    <div class="zy_content_box_configuration" v-html="indexMd">

        </div>
  </div>
</template>

<script>
import demo from './upRoll.md'
import downRoll from './downRoll.md'
import leftRoll from './leftRoll.md'
import indexMd from './index.md'
export default {
  data () {
    return {
      md: demo,
      downRoll: downRoll,
      leftRoll: leftRoll,
      indexMd: indexMd,
      listData: [
        {
          title: '无缝滚动第一行无缝滚动第一行',
          date: '2017-12-16'
        },
        {
          title: '无缝滚动第二行无缝滚动第二行',
          date: '2017-12-16'
        },
        {
          title: '无缝滚动第三行无缝滚动第三行',
          date: '2017-12-16'
        },
        {
          title: '无缝滚动第四行无缝滚动第四行',
          date: '2017-12-16'
        },
        {
          title: '无缝滚动第五行无缝滚动第五行',
          date: '2017-12-16'
        },
        {
          title: '无缝滚动第六行无缝滚动第六行',
          date: '2017-12-16'
        },
        {
          title: '无缝滚动第七行无缝滚动第七行',
          date: '2017-12-16'
        },
        {
          title: '无缝滚动第八行无缝滚动第八行',
          date: '2017-12-16'
        },
        {
          title: '无缝滚动第九行无缝滚动第九行',
          date: '2017-12-16'
        }
      ]
    }
  },
  computed: {
    classOption () {
      return {
        direction: 0
      }
    },
    optionLeft () {
      return {
        direction: 3,
        limitMoveNum: 4
      }
    }
  }
}
</script>
<style lang="less" scoped>
.seamless-warp {
  height: 100%;
  overflow: hidden;
  /* border: 1px solid red; */
}
.seamless-warp2 {
  overflow: hidden;
  height: 25px;
  width: 100%;
  ul.item {
    width: 100%;
    li {
      float: left;
      margin-right: 10px;
    }
  }
}
</style>

```html
<template>
    <vue-seamless-scroll :data="newsList" :class-option="optionLeft" class="seamless-warp2">
        <ul class="item">
            <li v-for="item in newsList" v-text="item.title"></li>
        </ul>
    </vue-seamless-scroll>
</template>
```
```javaseript
<script>
    export default {
        data () {
            return {
                newsList: [{
                      'title': 'A simple, seamless scrolling for Vue.js'
                    }, {
                      'title': 'A curated list of awesome things related to Vue.js'
                    }]
                 }
            },
            computed: {
                optionLeft () {
                    return {
                            direction: 2,
                            limitMoveNum: 2
                        }
                }
             }
       }
</script>
```
```css
<style lang="scss" scoped>
    .seamless-warp2 {
        overflow: hidden;
        height: 25px;
        width: 380px;
        ul.item {
            width: 580px;
            li {
                float: left;
                margin-right: 10px;
            }
        }
    }
</style>
```
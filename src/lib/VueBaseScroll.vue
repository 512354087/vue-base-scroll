<template>
  <div class="scroll-wrap" :style="{height}">
    <ul :style="animStyle">
      <slot v-for="item in newList" :item="item" name="item"></slot>
    </ul>
  </div>
</template>

<script>
  export default {
    name:'VueBaseScroll',
    props: {
      list: {
        type: Array,
        required: true
      },
      /**
       * @augments 滚动容器的高度
       */
      height: {
        type: String,
        default:'400px'
      },
      /**
       * @augments 每次滚动的距离
       */
      moveDistance: {
        type: String,
        defalut:'-40px'
      }
    },
    data() {
      return {
        newList: [],
        animStyle: {}
      }
    },
    watch:{
      list(val) {
        this.newList = val
      }
    },
    mounted() {
      this.$nextTick(() => {
        setInterval(this.scroll, 2000)
      })
    },
    methods: {
      scroll() {
        this.animStyle = {
          transition: 'all 0.5s',
          marginTop: this.moveDistance
        }
        setTimeout(() => {
          this.newList.push(this.newList[0]);
          this.newList.shift();
          this.animStyle = {}
        }, 1000)
      }
    }
  }
</script>

<style>
  .scroll-wrap {
    transition: all 0.5s;
    overflow: hidden; 
  }
</style>

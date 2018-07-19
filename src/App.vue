<template>
  <div id="app">
   <vue-base-scroll :list="plant_area_list" height="598px" >
      <li slot="item" slot-scope="{ item }" class="plants-item  flex">
        <span style="overflow: hidden;text-overflow:ellipsis;white-space: nowrap;">{{item.name}}</span>
        <span class="color-light_blue">{{item.area}}亩</span>
      </li>
    </vue-base-scroll>
                        
  </div>
</template>

<script>
import VueBaseScroll from "./lib/VueBaseScroll";
export default {
  name: "app",
  data() {
    return {
      plant_area_list: []
    };
  },
  components: {
    VueBaseScroll
  },
  created() {
    this.$nextTick(() => {
      this.plant_area_list = [
        {
          id: 1,
          name: "永宁镇",
          area: 15000
        },
        {
          id: 2,
          name: "华江镇",
          area: 15000
        },
        {
          id: 3,
          name: "坡贡镇",
          area: 14200
        },
        {
          id: 4,
          name: "上官镇",
          area: 15000
        },
        {
          id: 5,
          name: "岗乌镇",
          area: 15000
        }
      ];
    });
  }
};
</script>

<style>
</style>

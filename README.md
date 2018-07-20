# vue-base-scroll

> 一款vue的列表循环滚动组件

## Install

``` bash
# install dependencies
npm i vue-base-scroll --save
```
## Usage

* 第一种用法 
    > vue 入口文件 main.js 
``` js
   //全局组件
   import VueBaseScroll from 'vue-base-scroll';
   Vue.use(VueBaseScroll);  
```

* 第二种用法
    > vue页面 
``` js
   import VueBaseScroll from 'vue-base-scroll';
   //...
   components:{
       VueBaseScroll
   } 
   //...
```

 * Example
``` html
    <vue-base-scroll :list="plant_area_list" height="598px" >
        <li slot="item" slot-scope="{ item }" class="plants-item  flex">
            <span style="overflow: hidden;text-overflow:ellipsis;white-space: nowrap;">{{item.id}}</span>
            <span class="color-light_blue">{{item.name}}</span>
        </li>
    </vue-base-scroll>   
```

## API
``` js
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
```

## gitHub
 [Github](https://github.com/512354087/vue-base-scroll)


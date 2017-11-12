# vue-infinite-scroll
* 基于vue的轻量的上拉加加载更多组件。
* 占用内存小，性能好，样式好看，可扩展性强

## Install
```javascript
npm i vue2-infinite-scroll --save
cnpm i vue2-infinite-scroll --save  //国内镜像

```


##  Usage
```javascript

//放在页面的最底部
<Infinite v-on:infinite="infiniteMore" ></Infinite>

import Infinite from "vue2-infinite-scroll";

  components: {
    Infinite
  }
  
  
    infiniteMore($state) {
      this.axios .get("http://39.108.152.248:18080/member/v1/content/headline/list?type=3&pageSize=1&pageNo=1")
        .then(data => {
          this.aaa = this.aaa.concat(data.data.b.data);
          $state.loaded();   //这次加载完毕
          i++;
          if (i == 3) {
            $state.completed("全部加载完了");
          }
        });
    }
```


### API


## Other
* src下面的App.vue 有demo可以参考.
* 如果有其他问题或者版本上, 功能上不兼容的 邮件沟通 452216418@qq.com

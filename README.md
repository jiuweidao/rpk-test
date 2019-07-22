# rpk-test
rpk的测试demo

# 一、RPK入门

## 1.UI页面构成

```html
//ui
<template>
</template>

//页面脚本
<script>
//引用
import router from '@system.router'

 //js写于该内部
export default {
  private: {
    title: '示例页面'
  },
  //生命周期
  routeDetail () {
    // 跳转到应用内的某个页面，router用法详见：文档->接口->页面路由
    router.push ({
      uri: '/DemoDetail'
    })
  }
}
</script>

<style>
</style>
```



## 2.页面切换

### 2.1 href转跳

```html
<a href="/PageParams/receiveparams">跳转到接收参数页面</a>
```

注意需要在manifest配置page

```json
"router": {
    "entry": "Demo",
    "pages": {
      "Demo": {
        "component": "index"
      },
      "DemoDetail": {
        "component": "index"
      },
      "About": {
        "component": "index"
      }
    },
```

### 2.2页面路由

引入：

```javascript
import router from '@system.router' 或 const router = require('@system.router')
```

例子

```javascript
router.push({
  uri: '/about',
  params: {
    testId: '1'
  }
})
// open page by name
router.push({
  uri: 'About',
  params: {
    testId: '1'
  }
})
```

注意：

需要在manifest文件中添加page配置

方式同上

# vue项目demo

### 安装依赖可能遇到的问题及解决方法

#### 1 [vue项目中引用element ui](https://blog.csdn.net/QYHuiiQ/article/details/109013934)
```
cnpm i element-ui -S
```

#### 2 [查看webpack版本](https://blog.csdn.net/weixin_38617311/article/details/86822228)

#### 3 [Vue 中如何使用 less](https://www.jianshu.com/p/779ed2c368a3)
会有版本问题，未解决
```
// 下载
cnpm install --save less less-loader

// 卸载
npm uninstall less-loader
```

#### 4 [如何在vue中使用sass](https://www.jianshu.com/p/67f52071657d)
##### 报错最终解决办法
- package.json将sass改成下面这两个版本，这里用的是sass而不是node-sass，
- 将目录下的node_modules删除（包含文件太多了删的很慢，改名更快，弄好之后再删除）
- 然后npm install 或 cnpm install
```
    "sass": "1.26.2",
    "sass-loader": "^7.3.1"
```
使用
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210417115053552.png)


##### 其他可能的解决办法
会一直报错，网上的解决办法是[安装指定较低的版本](https://www.cnblogs.com/szqtiger/p/11599205.html)，或者各种卸载重装，但我的还是报错
```
// 卸载node-sass
npm uninstall node-sass

// 安装node-sass
npm install node-sass@4.14.1

// 卸载sass-loader
npm uninstall sass-loader

// 安装sass-loader
cnpm install sass-loader@7.3.1 --save-dev
```


#### 5 [vue项目中引入axios及使用](https://blog.csdn.net/marslover521/article/details/86593440)
```
cnpm install axios --save
```

#### 6 eslint常见问题
##### 6.1 error Strings must use singlequote quotes
单双引号问题，将双引号改为单引号
其他解决方法，修改eslintrc.js配置
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210417120911146.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxMjQzOTc5,size_16,color_FFFFFF,t_70)

#### 7 导入echart
[安装教程、使用教程demo](https://www.jianshu.com/p/fa42e697665d)
```
npm install echarts --save
```
echart版本过高，报错“export ‘default‘ (imported as ‘echarts‘) was not found in ‘echarts‘

##### [解决办法: 装一个低版本的](https://blog.csdn.net/Aom_yt/article/details/110947734)


卸载
```
npm uninstall echarts

```
安装
```
cnpm install echarts@4.9.0
```
全局使用
```
// 引入echarts
import echarts from 'echarts'
Vue.prototype.$echarts = echarts

```

#### 8 [导入nprogress](https://blog.csdn.net/wn1245343496/article/details/82151273)
安装
```
npm install --save nprogress
```
使用
```
//导入
import NProgress from 'nprogress'
import 'nprogress/nprogress.css'

router.beforeEach((to, from, next) => {
  NProgress.start()
  next()
})

router.afterEach(() => {
  NProgress.done()
})
```

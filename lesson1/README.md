## Nuxt.js 环境的搭建 
1. 全局安装vue-cli: npm install vue-cli -g   
    查看版本号  vue -V

2. 初始化一个项目  vue init nuxt/starter   

3. 一个vue的组件库  vant -- youzan出品  支持ts，支持ssr 

4. 目录结构   
    |-- .nuxt                            // Nuxt自动生成，临时的用于编辑的文件，build   
    |-- assets                           // 用于组织未编译的静态资源入LESS、SASS 或 JavaScript   
    |-- components                       // 用于自己编写的Vue组件，比如滚动组件，日历组件，分页组件  
    |-- layouts                          // 布局目录，用于组织应用的布局组件，不可更改。  
    |-- middleware                       // 用于存放中间件   
    |-- pages                            // 用于存放写的页面，我们主要的工作区域   
    |-- plugins                          // 用于存放JavaScript插件的地方   
    |-- static                           // 用于存放静态资源文件，比如图片   
    |-- store                            // 用于组织应用的Vuex 状态管理。   
    |-- .editorconfig                    // 开发工具格式配置   
    |-- .eslintrc.js                     // ESLint的配置文件，用于检查代码格式  
    |-- .gitignore                       // 配置git不上传的文件   
    |-- nuxt.config.json                 // 用于组织Nuxt.js应用的个性化配置，已覆盖默认配置   
    |-- package-lock.json                // npm自动生成，用于帮助package的统一性设置的，yarn也有相同的操作  
    |-- package-lock.json                // npm自动生成，用于帮助package的统一性设置的，yarn也有相同的操作  
    |-- package.json                     // npm包管理配置文件  

5. 常用配置   
a. ip和端口  /package.json   
```
"config":{
    "nuxt":{
        "host":"127.0.0.1",
        "port":"1818"
    }
},
```

b. 全局样式的配置  /nuxt.config.js   
```
 css:['~assets/css/normailze.css'],    
```
编写assets/css/normailze.css   

c. 配置webpack的loader     
在nuxt.config.js里是可以对webpack的基本配置进行覆盖的  在build下可进行对应的配置     

6. Nuxt的路由配置和参数传递    
a. 路由的跳转    
```
<nuxt-link :to="{name: 'index'}"></nuxt-link>
```

b. 路由传参  和vue基本一致   

c. 动态路由  
动态路由以page文件夹下 _params.vue 为模板名称  
路由校验    
```
export default {
  validate({params}) {
    return /^\d+$/.test(params.newsId)
  }
}
``` 

7. 路由切换的动画效果  
a. 全局添加  编写css动画  
注意，需要使用nuxt-link跳转才会添加动画   
```
.page-enter-active, page-leave-active {
  transition: opacity 2s;
}
.page-enter, page-leave-active {
  opacity: 0;
}
```

b. 局部动画  使用 name 代替 page  ，并在对应页面中添加 transition: 'test' 属性指定使用这个动画   
```
.test-enter-active, test-leave-active {
  transition: all 2s;
  font-size: 12px;
}
.test-enter, test-leave-active {
  opacity: 0;
  font-size: 40px;
}

export default {
  transition: 'test'
}
```

8. 默认模板和默认布局  

a. 默认模板: 根目录下建立  app.js  
    head 中的内容不用添加， 使用  {{HEAD}}  引入
    添加的内容是 {{APP}} 来表示

b. 默认布局  layouts/default.vue

9. 错误页面  layouts/error.vue  页面  
    可根据 props 中的 error  来判断  error.statusCode === 404 来做页面装填判断

10. title 和 content 独立设置   
<nuxt-lick :to="{name: 'news-id', params: {id: 123, title: '资讯详情'}}"></nuxt-link>   

data() {   
    return{   
        title: $toute.params.title   
    }   
},   
head() {   
    return{   
        title: this.title,  
        meta: [    
            <!-- hid为唯一标识，想覆盖全局的必须写相同的唯一标示 -->   
            {hid: 'aaa', name: 'news1', content: 'tree new bee'}   
        ]   
    }  
}   

11. asyncData的使用
```
asyncData() {
    return axios.get('/api/news')
           .then( res => {
               return {info: res.data}
           })
}

async asyncData() {
    let {data} = await axios.get('/api);
    return {info: data}
}
```

12. 打包 npm run generate





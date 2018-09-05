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


# 使用文档
## 项目初始化

1. 全局安装vue  npm install -g vue  |  cnpm install -g vue
2. 安装@form-create/ant-design-vue、ant-design-vue  根据package.json安装依赖
3. main.js：项目入口文件，项目中所有的页面都会加载main.js。main.js的三个作用：
   3.1. 实例化vue
   3.2. 放置项目中经常会用到的插件和CSS样式 
4. App.vue：根组件，模板就是组件App.vue中的template中的内容，所有页面都是在App.vue下进行切换的，可以理解为所有的路由也是App.vue的子组件 
5. src/router：路由配置 ，所有通过地址栏能够访问的页面必须在router中进行注册
```html
  {
    path: '/',  路由地址
    name: 'Home',路由名称
    component: () => import('../pages')  页面路径，默认找pages目录下index文件
  },
```
6. pages：组件，页面存放的位置
7. store：存储数据和管理数据，远程获取数据、存储数据，使用Vuex.Store
8. api：接口调用
9. assets：静态文件存放
10. components：公共组件
### 1. proxy 配置代理
```html
  proxy: {
    "/api": {
    target: `http://${ip地址}:端口号`,
    changeOrigin: true,
    },
  },
```
备注：更改该目录后，项目记得重启

### 2. src 项目主入口
```html
  proxy: {
    "/api": {
    target: `http://${ip地址}:端口号`,
    changeOrigin: true,
    },
  },
```
备注：更改该目录后，项目记得重启


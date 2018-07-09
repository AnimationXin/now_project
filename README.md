#jsyj-web-admin

## 使用

```
# 安装
yarn install
# 调试
yarn run dev
# 打包
yarn run build
```

## 代码结构

```shell
src
├── app.vue            # app入口，无需修改
├── assets
│   └── logo.png
├── components         # 公共组件定义在此处
├── config.js          # 项目配置文件
├── filters.js         # 过滤器
├── main.js            # vue入口
├── router.js          # 路由
├── services
│   └── dataService.js # restful api全部定义在此文件中
├── store              # vuex 页面数据操作逻辑写在此处
│   ├── actions.js    
│   ├── getters.js
│   ├── index.js
│   ├── modules        # 按模块划分
│   │   └── test.js
│   ├── mutation-types.js
│   ├── mutations.js
│   └── state.js
└── views              # 页面
    ├── layout         # 网站布局
    │   ├── body.vue
    │   ├── footer.vue
    │   ├── header.vue
    │   └── shell.vue
    └── test           # 功能页面
        └── index.vue  # 功能页面文件夹必须定义index.vue文件
```



## 约定

为了更好的协作，请按如下约定进行编码。约定可以探讨，请勿自行创作。

**大家开发过程中请保持基本的代码风格一致，有较大冲突的地方请提出来，我们统一协商处理。**

#### 命名

```shell
文件名: defineFile
变量名: defineVar
css  : this-is-css {}

命名必须能够自解释，请勿使用诸如 button-1、var1的命名方式。
```

#### 后端交互
![Image_text](https://raw.githubusercontent.com/AnimationXin/JavaScript/master/%E4%BB%8E0%E5%BC%80%E5%A7%8B/images/QQ%E5%9B%BE%E7%89%8720180709193807.png)

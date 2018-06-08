## 一、发送 AJAX 请求

### 1.简介

vue 本身不支持发送ajax请求，需要使用vue-resource(在vue2.0 中已不在更新)、axios(vue2.0 中推荐使用)等插件实现

axios 是基于 Promise 的 HTTP 请求客户端，用来发送请求，也是 vue2.0 官方推荐使用的，同时在vue2.0中不在对 vue-resource 进行维护升级。

参考：[https://github.com/axios/axios](https://github.com/axios/axios)

### 2.使用axios发送ajax请求

#### 2.1 安装axios并引入

```
npm install --save-dev axios

也可以直接下载 axios.min.js 文件
```

#### 2.2 基本用法

```
axios([options])
axios.get(url, [,options])
    传参方式：
        1. 通过url传参
        2. 通过选项参数params传参，他会自动将参数拼接到url上
axios.post(url, data, [options])
```
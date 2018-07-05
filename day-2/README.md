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

`axios` 本身不支持发送跨域请求，没有响应的API，作者暂时也没计划在 `axios` 中添加支持发送跨域请求，所以只能使用第三方库。

### 3. 使用 vue-resource 进行跨域请求。

#### 3.1 安装 vue-resource 并引入

```
npm install --save-dev vue-resource
```

#### 3.2 基本用法

使用 `this.$http` 发送请求

    this.$http.get(url, [config])
    this.$http.head(url, [config])
    this.$http.delete(url, [config])
    this.$http.jsonp(url, [config])
    this.$http.post(url, [body], [config])
    this.$http.put(url, [body], [config])
    this.$http.patch(url, [body], [config])

注意：JSONP，修改 callback 参数名，传入 `jsonp` 可以去修改

```js
{
    jsonp: 'cb'
}
```

## 二、Vue生命周期

Vue实例从创建到销毁的过程，称为生命周期(也叫做钩子)，共有八个阶段。

- beforeCreate: 组件示例初始化后，未对数据进行监测以及事件的绑定，触发此方法
- created(常用): 组件示例初始化后，已对数据进行监测以及事件的绑定，触发此方法
- beforeMount: 组件示例初始化后，模板挂载之前，未对模板进行编译，触发此方法
- mounted(常用): 组件示例初始化后，模板挂载之后，已对模板进行编译，触发此方法
- beforeUpdate: 对组件更新之前触发此方法
- updated: 对组件更新完毕后触发此方法
- beforeDestroy: 调用 `vm.$destory()` 方法销毁组件之前，触发此方法
- destroyed: 调用 `vm.$destory()` 方法销毁组件之后，触发此方法

## 三、计算属性
# API
## Select

|   参数    |   说明   |   类型 |  默认值  | 必填|备注
|----------|------|-------|---------|-------|-----|
|name      |组件名称，提交到后端的字段|string|`-`|Y
|label     |标签文本|string|`-`|Y
|hidden    |组件隐藏|boolean|`-`|N
|placeholder|表单项输入说明          |string|`-`|N
|defaultValue|默认值|string|`-`|N
|itemLayout  |表单元素宽度占比|`{}`|`-`|N|
|disabeled|是否禁用|boolean|`-`|N
|rules |验证规则|`[]`|`-`|N
|style |组件样式|`{}`|`-`|N
|allowClear   |点击清楚图标删除内容|boolean|`-`|N
|`data`   |组件数据源|`[]`|`[]`|N
|`remote`   |组件异步获取需要配置的请求参数|`{}`|`-`|N


## Select.remote
|   参数    |   说明   |   类型 | 必填 | 默认值
|----------|------|-------|---------|-------
|url |异步获取地址|string|Y|
|params |异步获取参数|string|N
|key |指定返回数据中取的key值名称|string|N
|value |必选时，空格是否被视为错误|string|N

## Select.rules
|   参数    |   说明   |   类型 |  案例
|----------|------|-------|---------|-------
|whitespace|必选时，空格是否被视为错误|boolean|{whitespace:true,message:'错误提示文字''}
|len     |字段长度|string|{len:10,message:'错误提示文字''}
|max    |最大长度|boolean|{max:20,message:'错误提示文字''}
|min|最小长度          |string|{min:10,message:'错误提示文字''}
|required|是否必填|string|{required:true,message:'错误提示文字''}
|pattern  |自定义正则表达式校验|`{}`|{pattern:表达式,message:'错误提示文字''}



## Select.event
|   参数    |   说明   |   类型
|----------|------|-------|
|@change|组件改变事件|function

## Example
### 静态数据
```html
<template>
  <hs-select
    placeholder="请选择"
    label="下拉框"
    name="key4"
    defaultValue="1"
    :itemLayout="itemLayout"
    :data="selectItems"
    :rules="[
            {required: true, message: '请选择444' },
           ]"
    @change="handleClick"/>
</template>
```
### 远程数据获取
```html
<template>
  <hs-select
    label="下拉框-远程"
    name="remote"
    defaultValue="1"
    :itemLayout="itemLayout"
    :remote="{url:'/api/product/selectSupplier',key:'supplierCode',value:'supplierName'}"
    :rules="[
            {required: true, message: '请选择远程数据' },
           ]"
    @change="handleClick"/>
</template>
```

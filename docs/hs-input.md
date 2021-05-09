# API
## Input

|   参数    |   说明   |   类型 |  默认值  | 必填|备注
|----------|------|-------|---------|-------|-----|
|name      |组件名称，提交到后端的字段|string|`-`|Y
|label     |标签文本|string|`-`|Y
|hidden    |组件隐藏|boolean|`-`|N
|placeholder|表单项输入说明          |string|`-`|N
|defaultValue|默认值|string|`-`|N
|itemLayout  |表单元素宽度占比|`{}`|`-`|N|
|disabled|是否禁用|boolean|`-`|N
|rules |验证规则|`[]`|`-`|N
|style |组件样式|`{}`|`-`|N
|allowClear   |点击清楚图标删除内容|boolean|`-`|N


## Input.rules
|   参数    |   说明   |   类型 |  案例 
|----------|------|-------|---------|-------
|whitespace|必选时，空格是否被视为错误|boolean|{whitespace:true,message:'错误提示文字''}
|len     |字段长度|string|{len:10,message:'错误提示文字''}
|max    |最大长度|boolean|{max:20,message:'错误提示文字''}
|min|最小长度          |string|{min:10,message:'错误提示文字''}
|required|是否必填|string|{required:true,message:'错误提示文字''}
|pattern  |自定义正则表达式校验|`{}`|{pattern:表达式,message:'错误提示文字''}



## Input.event
|   参数    |   说明   |   类型
|----------|------|-------|
|@change|组件改变事件|function
|@search|组件搜索事件|function

## Example  
### 文本框
```html
<template>
  <Button>111</Button>
  <hs-inputs
    placeholder="文本框"
    label="文本框1"
    name="key1"
    defaultValue="111"
    :itemLayout="itemLayout"
    :rules="[
       {whitespace:true,message:'不能全为空格'},
       {required: true, message: 'key1不能为空' },
       { min: 5, message: '最小长度为5' },
       { len: 10, message: '长度为10' },
     ]"
    @change="handleClick"/>
</template>
<script>
  console.log(111);
</script>
```
### 带搜索按钮文本框
```html
<template>
  <hs-inputs-search
    label="带搜索文本框"
    placeholder="带搜索按钮的文本框"
    :itemLayout="itemLayout"
    defaultValue="111"
    :rules="[
           {whitespace:true,message:'不能全为空格'},
           {required: true, message: 'key1不能为空' },
           { min: 5, message: '最小长度为5' },
           { len: 10, message: '长度为10' },
           ]"
    @change="handleClick"
    @search="handleClick"/>
</template>
```

# API
## RangePicker

|   参数    |   说明   |   类型 |  默认值  | 必填|备注
|----------|------|-------|---------|-------|-----|
|name      |组件名称，提交到后端的字段|string|`-`|Y
|label     |标签文本|string|`-`|Y
|hidden    |组件隐藏|boolean|`-`|N
|placeholder|表单项输入说明          |string|`-`|N
|`defaultValue`|默认值|[]|`-`|N
|itemLayout  |表单元素宽度占比|`{}`|`-`|N|
|disabled|是否禁用|boolean|`-`|N
|rules |验证规则|`[]`|`-`|N
|style |组件样式|`{}`|`-`|N
|allowClear   |点击清楚图标删除内容|boolean|`-`|N


## RangePicker.rules
|   参数    |   说明   |   类型 |  案例
|----------|------|-------|---------|-------
|required|是否必填|string|{required:true,message:'错误提示文字''}



## RangePicker.event
|   参数    |   说明   |   类型
|----------|------|-------|
|@change|组件改变事件|function

## Example
### RangePicker
```html
<template>
  <hs-range-picker
    label="时间范围"
    name="key12"
    :defaultValue="['2020-04-22','2020-05-01']"
    :itemLayout="itemLayout"
    :rules="[
          {required: true, message: '请选择开始时间和结束时间' },
         ]"
    @change="handleClick"/>
</template>
```

# API
## Advanced-tree

|   参数    |   说明   |   类型 |  默认值  | 必填
|----------|------|-------|---------|-------|-----|
|showLine|是否展示连接线|boolean|TRUE|N
|checkable     |节点前添加 Checkbox 复选框|boolean|TRUE|N
|iconType    |TreeNode title 前的图标|string|carry-out|N
|switcherIcon   |自定义树节点的展开/折叠图标|string|minus-square|N
|operation   |自定义操作项|object|null|N

|dataSource|数据源          |`[]`|`-`|Y
|propsExpandedKeys|默认展开指定的树节点|`string[] | number[]`|`-`|N
|propsCheckKeys  |默认选中复选框的树节点|`string[] | number[]`|[]|N



## Advanced-search event
|   参数    |   说明   |   类型
|----------|------|-------|
|loadResourceData|树加载事件|function|`-`|N
|check|选中事件|function|`-`|N

## Example  
### 
```html
<template>
  <div>
    <hs-advanced-tree
      :showLine="true"
      :checkable="true"
      iconType="carry-out"
      switcherIcon="minus-square"
      :dataSource="treeData"
      :operation="[{name:'新增',action:''},{name:'编辑',action:''},{name:'删除',action:''},{name:'刷新',action:''}]"
      :propsExpandedKeys="propsExpandedKeys"
      :propsCheckKeys="propsCheckKeys"
      :loadResourceData="loadResourceData"
      :check="handleCheck">
    </hs-advanced-tree>
  </div>
</template>

<script>
  const treeData = [
    {
      title: '0-0',
      key: '0-0',
      child:true,
      children: [
        {
          title: '0-0-0',
          key: '0-0-',
          children: [
            { title: '0-0-0-0', key: '0-0-0-0' },
            { title: '0-0-0-1', key: '0-0-0-1' },
            { title: '0-0-0-2', key: '0-0-0-2' },
          ],
        },
        {
          title: '0-0-1',
          key: '0-0-1',
        },
        {
          title: '0-0-2',
          key: '0-0-2',
        },
      ],
    },
    {
      title: '0-1',
      key: '0-1',
      child:true,
      // children: [
      //   { title: '0-1-0-0', key: '0-1-0-0' },
      //   { title: '0-1-0-1', key: '0-1-0-1' },
      //   { title: '0-1-0-2', key: '0-1-0-2' },
      // ],
    },
    {
      title: '0-2',
      key: '0-2',
    },
  ];
  export default {
    name: "index",
    data(){
      return {
        treeData:treeData,
        propsExpandedKeys:['0-0'],
        propsCheckKeys:['0-0'],
        expandedKeys:[],
      }
    },
    mounted(){
    },
    methods:{
      loadResourceData(treeNode){
        return new Promise(resolve => {
          if (treeNode.dataRef.children) {
            resolve();
            return;
          }
          setTimeout(() => {
            treeNode.dataRef.children = [
              { title: 'Child Node', key: `${treeNode.eventKey}-0` },
              { title: 'Child Node', key: `${treeNode.eventKey}-1` },
            ];
            this.treeData = [...this.treeData];
            resolve();
          }, 1000);
        });
      },
      handleCheck(checkNode){
        console.log("checkNode",checkNode);
      }
    },

  }
</script>

<style lang="less">

</style>


<style lang="less">

</style>


```


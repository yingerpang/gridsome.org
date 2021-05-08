# API
## Advanced-search

|   参数    |   说明   |   类型 |  默认值  | 必填
|----------|------|-------|---------|-------|-----|
|showOption|是否显示左边下拉框|boolean|TRUE|N
|showSearch     |是否显示右边搜索按钮|boolean|TRUE|N
|showSplit    |是否显示列表分割线|boolean|FALSE|N
|allowClear   |点击清楚图标删除内容|boolean|TRUE|N
|renderHeader|自定义搜索结果页头部          |`function|node`|`-`|N
|renderItem|自定义搜索列表项|`function|node`|`-`|N
|size  |搜索框大小|string|small|N
|styles  |搜索框样式|`{}`|`-`|N|
|assignKey|指定搜索列表key|string|`-`|N
|searchResult   |搜索结果数据|object|`-`|Y|


## Advanced-search select
|   参数    |   说明   |   类型 |  默认值  | 必填
|----------|------|-------|---------|-------|-----|
|optionKey |指定下拉框key|string|`key`|N
|optionValue |指定下拉框value|string|`value`|N
|optionData   |下拉框数据|array|`-`|N
|optionDefaultValue   |下拉框默认值|string|`-`|N

## Advanced-search event
|   参数    |   说明   |   类型
|----------|------|-------|
|@change   |搜索框改变事件|function|`-`|N
|@search   |搜索框搜索事件|function|`-`|N

## Example  
###
```html
<template>
  <div>
    <hs-advanced-search
      optionDefaultVal="全部"
      :optionData="selectItems"
      :showOption="true"
      :showSearch="true"
      :showLoadMore="true"
      :showSplit="false"
      assignKey="title"
      size="large"
      :styles="{width:'500px'}"
      :searchResult="searchResult"
      @change="handleOptionChange"
      @search="handleOptionChange">
    </hs-advanced-search>
  </div>
</template>

<script>
  document.cookie = 'haishu-sc=' + 'A4836971316F3669C86F330D606A2125E0489656391489F87E1C9C90D9F1B8F90FBE54AF034E5B76BFA36AC26FD0A23939B4190CD70246B347469E13289DD6F43D204007734800DF11A57DA6BE0CA5E9';
  export default {
    name: "index",
    data(){
      return {
        itemLayout:{labelCol:{sm:7},wrapperCol:{sm:17}},
        form: this.$form.createForm(this),
        selectItems:[{key:'全部',value:'全部'},{key:'可见',value:'可见'}],
        radioItems:[],
        searchResult: {data:[],count:0},
        timeout:null,
      }
    },
    mounted(){
    },
    methods:{
      onSearch(e) {
      },
      handleOptionChange(keywords){
        this.loadingList(keywords)
      },
      //自定义搜索列表项
      renderItem(item,index){
        return <div>{item.title}</div>
      },
      //自定义搜索列表头部
      renderHeader(){
        return <div>这是头部</div>
      },
      //加载搜索列表数据
      loadingList(keywords){
        this.loading=true;
        let remote={url:'/elasticsearch/pubapi/searchkey/searchGroup',params:{keywords}}
        this.$store.dispatch('form/remoteData', remote).then(res=>{
          this.searchResult=res;
        })
      },
    }
  }
</script>

<style lang="less">

</style>

```


<template>
  <div id="app">
    <mysection btn-value="查询" :datalist="texts"></mysection>
    <mysection btn-value="搜索" :datalist="nums"></mysection>
    <router-view/>
  </div>
</template>

<script>
import mysection from "./components/section.vue"
export default {
  name: 'app',
  data(){
    return{
      texts:["html","css","javascript","angular","react","vue","jquery","nodejs","bootstrap"],
      nums:["1","2","3","4","5","6","7","8","9"]
    }
  },
  components:{
    mysection
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

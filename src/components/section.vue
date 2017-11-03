<template>
  <div class="section"> 
     <section class="warp">
       <div class="searchIpt clearFix">
         <div class="clearFix chinput">
           <input type="text" class="keyWord" :value="val" @click="selectShow=!selectShow" />
           <input type="button" class="btn" :value="btnValue" />
         </div>
         <sectlist v-show="selectShow" :datalist="datalist" v-on:receive="changeValue"
         ></sectlist>
        <!--  <sectlist v-show="selectShow" :datalist="nums"></sectlist> -->
       </div>
     </section>
  </div>
</template>

<script>
import sectlist from "./sectlist.vue"
export default {
  name: 'section',
  props:{
      datalist:{
        type:Array,
        default:[]
      },
      btnValue:{
        type:String
      }
    },
  data () {
    return {
      selectShow:false,
      val:""
    }
  },
  methods:{
    changeValue(value){
      this.val = value;
    }
  },
  components:{
    sectlist
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
.section {
  width: 400px;
  // min-height: 300px;
  margin: 0 auto;
  background-color: #ccc;
  padding: 20px 0;
  .warp {
    width: 60%;
    height: 100%;
    margin:0 auto;
    padding: 0 10px;
    background-color: pink;
    border-radius: 5px;
    overflow: hidden;
    .chinput {
      width: 100%;
      padding: 10px 0;
      display: flex;
      input {
        height: 28px;
        line-height: 28px;
        border-radius: 20px;
        border:none;
        outline: none;
        -webkit-appearance: none;
      }
      .keyWord{
        flex:7 ;
        text-indent: 10px;
      }
      .btn {
        flex:1;
        color: #fff;
        background: #999;
        padding:0 10px;
        cursor: pointer;
      }
    }
  }
}

</style>

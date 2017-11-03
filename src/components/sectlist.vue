<template>
	<ul class="list">
           <li v-for="item in datalist" @click="selectValue(item)" key>{{item}}</li>
    </ul>
</template>

<script >
	export default {
		props:{
			datalist:{
				type:Array,
				default:[]
			}
		},
		data () {
		    return {
		    }
		},
		methods:{
			selectValue(item){
				this.$emit("receive",item)
			}
		}
	}
</script>

<style scoped lang="less">
.list {
      li {
        padding: 5px 0 5px 10px;
        text-align: left;
        cursor: pointer;
        border-radius: 5px;
      }
      li:hover{
        background-color: #fff;
      }
    }
    
</style>
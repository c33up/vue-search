<template>
  <div class="about">
    <button class="btn" v-on:click="addData">加载数据</button>
    <div v-for="item in list" :key="item.group" class="groups">
        <expend-list  :items="item"/>
    </div>
  </div>
</template>
<script>
import ExpendList from '@/components/ListExpend'
import { exists } from 'fs';
export default {
  name:'About',
  components:{
    ExpendList
  },
  data () {
    return {
      list:[]
    }
  },methods: {
    addData:function(){
        for(var i=0;i<10;i++){
          var obj={};
          obj.groups=i;
          obj.list=[];
          for(var x=20;x>1;x--){
            if(x%i==0){
              obj.list.push(x);
            }
          }
          this.list.push(obj);
        }
        console.table(this.list)
    }
  }
}
</script>

<style>
.groups{
  background-color: #eee;
  padding-bottom: 10px;
}
.btn{
  padding: 10px 20px;
  background-color: cadetblue;
  color: white;
  margin-bottom: 10px;
}
</style>

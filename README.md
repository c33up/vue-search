Vue学习：
这是一个简单的搜索组件
主要学习父子组件间的传值：
search.vue中定义方法，父组件实现该方法来获取子件的值，
而父组件通过progs传值给子件；

子组件：
<template>
    <div id="search">
        <div class="search">
            <form class="search_from">
                <input type="button" class="search_btn" 
                @click="searchClick"/>
                <input type="text" class="search_key" 
                :placeholder="tip"
                 v-model="inputTxt"
                 v-on:keyup.enter="searchClick"/>
            </form>
        </div>
    </div>
</template>
<script>
export default {
    name:"Search",
    props:{
        tip:{
            type:String,
            default:"请输入关键字"
        }
    },
    data () {
        return {
             inputTxt:'',
        }
    },
    methods:{
        searchClick:function(){
            this.$emit("doSearch",this.inputTxt)
        }
    }
}
</script>

父组件：
<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <Search tip="123" @doSearch="search"></Search>
    <h1>{{words}}</h1>
  </div>
</template>

<script>
// @ is an alias to /src
import Search from '@/components/Search.vue'

export default {
  name: 'home',
  components: {
    Search
  },
  data () {
    return {
      words:''
    }
  },
  methods: {
    search:function(param){
      this.words=param;
    }
  }
}
</script>


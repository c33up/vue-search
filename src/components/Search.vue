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
<style scoped>

.search_from{
    display: flex;
    flex-direction: row;
    align-items: center;
    border: 1px solid #ccc;
    border-radius: 10px;
    width: 224px;
}

.search_btn{
    background-color: transparent;
    border: none;
    background: url("../assets/sousuo.png") left center no-repeat;
    margin: 0 0 0 10px; 
    outline-style: none;
}

.search_key{
    background-color: transparent;
    outline-style: none;
    margin: 0 10px 0 10px;
    border: none;
}


</style>


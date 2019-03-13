<template>
    <div id="list">
        <div class="group" @click="showItem" >
            <img :src="show?require('../assets/arr_dowm.png'):
            require('../assets/arr_right.png')"/>
            {{items.groups}}</div>
        <ul v-if="show" class="list">
            <li
            class="item" 
            v-for="(item,index) in items.list" :key="index">
            {{item}}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name:'ListExpend',
    props: ['items'],
    data () {
        return {
             show:false,
        }
    },
    methods: {
        showItem:function(){
            this.show=!this.show;
        }
    }
}
</script>

<style scoped>
.group{
    width: 100%;
    color: black;
    text-align: left;
    border-bottom: 1px solid #333;
    padding: 10px 0;
    background-color: pink;
}
.list{
    padding: 0;
}
.item{
    padding: 0;
    margin: 0;
    text-align: left;
    list-style: none;
    padding: 5px 5px;
    border-bottom: 1px solid #999;
    background-color: aliceblue;
}

</style>


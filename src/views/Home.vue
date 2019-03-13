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

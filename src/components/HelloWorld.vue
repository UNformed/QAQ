<template>
  <div>
    <button type="button" @click="getData()">点击获取数据</button>
    <div class="json">
      {{json}}
    </div>
  </div>
</template>

<script>
import {Service} from '../axios/index.js'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      json:''
    }
  },
  methods: {
    getData() {
      console.log(1)
      let that = this
      Service.get('/getdata').then(res => {
        this.json = res
        console.log(res)
      })
    }
  },
  mounted(){
    getData();
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

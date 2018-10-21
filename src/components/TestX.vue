
<template id="title1">
  <div>
  <div v-for="i in range(aa.length)">
    <h1>测试{{i}}</h1>
  </div>
  </div>


</template>
<!--复制模板-->

<script>
  import axios from 'axios'
export default {
  name: 'TestX',
  // props:['user'],
  data () {
    return {
      id:1,
      aa:[1,2,3,4,5],
      bb:0,
      props:["user","token"],
      user:{
        'id':'1',
        "username":"棕色试剂瓶",
        "usericno":"http://n3-q.mafengwo.net/s10/M00/0F/9B/wKgBZ1iUpFWAbScxAAC2Vfg46fo14.jpeg?imageMogr2%2Fthumbnail%2F%21200x200r%2Fgravity%2FCenter%2Fcrop%2F%21200x200%2Fquality%2F90",
        "sex":"男",
        "mark":"15",
        "birthday":"1997-6-2",
        "state":"大庆",
        "content":"起始",
      },
      msg: 'Welcome to Your Vue.js App'
    }
  },
  created(){
    sessionStorage.setItem("token","congqianyouzuoshan")
    sessionStorage.setItem("id","1")
    this.token = "gzw"
    console.log(this.props)
},

  method:{
    // 显示热门游记
    showtrvelnotes:function () {
      var vm  = this
      axios.get(' http://127.0.0.1:8000/user/myfocusnum/' + vm.user.id + '/')
        .then(function (response) {
          // vm.some = response.data
          // alert(vm.some)
          // 获取所有数据
          // vm.alldata = response.data
        })
        .catch(function (error) {
          return error
        })
    }
  }
}
</script>
<style scoped>
</style>

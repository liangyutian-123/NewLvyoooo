<template id="content-right">
  <div class="col-md-8 post-window">
    <ul class="nav nav-tabs card">
      <li role="presentation" @click='choose($event)'><router-link to="/hottravelnote"><a href="javascrapy:;">热门游记</a></router-link></li>
      <li role="presentation" @click='choose($event)'><router-link to="/newest"><a href="javascrapy:;" @click="newest">最新发布</a></router-link></li>
      <li role="presentation" @click='choose($event)'><router-link to="/newstrategy"><a href="javascrapy:;">新鲜攻略</a></router-link></li>
    </ul>
    <!--热门游记-->
    <!--邮寄详情模态框-->
    <motaikuang @hidden="hiddenshow" v-if="motaikuang" v-model="travelnoteid" :travelnoteid="travelnoteid"></motaikuang>
    <div class="father">
      <router-view/>
    </div>

    <div class="stay">
      <!--<div class="focus-top"><a href="####"><img src="../assets/images/回到顶部.png" alt=""></a></div>-->
      <!--<div class="w-travelnotes"><a href="####"><img src="../assets/images/" alt=""></a></div>-->
      <!--<div class="w-strategy"><a href="####"><img src="../assets/images/攻略.png" alt="" width="35px" height="35px"></a></div>-->
    </div>
    <!--<div class="container page">-->
    <!--<button class="btn before-page">上一页</button>-->
    <!--<div class="lin_page_index btn ">-->
    <!--<a class="btn btn-default padding" href="####"></a>-->
    <!--</div>-->
    <!--<button class="btn next-page">下一页</button>-->
    <!--<div class="btn ">共<span style="color: #549c55"></span>页</div>-->
    <!--</div>-->

  </div>
</template>

<!--复制模板-->

<script>
  export default {
    name: 'ContentRight',
    data() {
      return {
        travel: [],
        id: 1,
        aa: 1,
        bb: 0,
        travelnoteid:'1',
        motaikuang:false,
        props: ["user", "token"],
        travels:[{
          "id":"1",
          "title":"苏州，一座文化古城。。。。",
          "imageurls":"https://b1-q.mafengwo.net/s12/M00/39/F7/wKgED1ujYTGAUH0zAAhVpG44zZE10.jpeg?imageMogr2%2Finterlace%2F1",
          "content":"这里是简介",
          "good":"231",
          "view":"300",
          "state":"苏州",
          "cover_url":"https://p4-q.mafengwo.net/s12/M00/71/49/wKgED1vF6liAG23NAASqHYuzB4U99.jpeg?imageMogr2%2Finterlace%2F1",
          "usericno":"https://b1-q.mafengwo.net/s12/M00/39/F7/wKgED1ujYTGAUH0zAAhVpG44zZE10.jpeg?imageMogr2%2Finterlace%2F1",
        },
        ],
        travel1:[{
          "id":"1",
          "title":"开封，一座文化古城。。。。",
          "imageurls":"https://b1-q.mafengwo.net/s12/M00/39/F7/wKgED1ujYTGAUH0zAAhVpG44zZE10.jpeg?imageMogr2%2Finterlace%2F1",
          "content":"这里是简介",
          "good":"231",
          "view":"300",
          "state":"苏州",
          "cover_url":"https://b1-q.mafengwo.net/s12/M00/39/F7/wKgED1ujYTGAUH0zAAhVpG44zZE10.jpeg?imageMogr2%2Finterlace%2F1",
          "usericno":"https://b1-q.mafengwo.net/s12/M00/39/F7/wKgED1ujYTGAUH0zAAhVpG44zZE10.jpeg?imageMogr2%2Finterlace%2F1",
        },
        ],
        user: {
          'id': '1',
          "username": "棕色试剂瓶",
          "usericno": "http://n3-q.mafengwo.net/s10/M00/0F/9B/wKgBZ1iUpFWAbScxAAC2Vfg46fo14.jpeg?imageMogr2%2Fthumbnail%2F%21200x200r%2Fgravity%2FCenter%2Fcrop%2F%21200x200%2Fquality%2F90",
          "sex": "男",
          "mark": "15",
          "birthday": "1997-6-2",
          "state": "大庆",
          "content": "起始",
        },
        msg: 'Welcome to Your Vue.js App'
      }
    },
    created() {
      // sessionStorage.setItem("token", "congqianyouzuoshan")
      // sessionStorage.setItem("id", "1")
      // this.token = "gzw"
      // console.log(this.props)
    },


    methods:{
      // 点击最新发布
      newest:function(){
        var vm = this
        vm.$set(vm.travels,vm.travel1,1)
        // vm.travels = vm.travel1
        // axios.get(' http://127.0.0.1:8000/travelnote/gettravelnotenewest/')
        //   .then(function (response) {
        //     // vm.some = response.data
        //
        //     console.log(vm.some)
        //     // 获取所有数据
        //     // vm.alldata = response.data
        //   })
        //   .catch(function (error) {
        //     return error
        //   })
      },
      // 点击显示模态框
      choose(event){
        event.target.className="active"
      },
      showthat(event){

        console.log(event.currentTarget); // event.currentTarget获取当前点击元素DOM
        this.travelnoteid = event.currentTarget.id
        console.log(event.currentTarget.id); // event.currentTarget获取当前点击元素DOM
        this.motaikuang = true
      },
      // 被动执行隐藏模态框
      hiddenshow(){
        let that = this;
        // 将其值修改为false
        that.motaikuang = ! that.motaikuang
      },
      getalltravelnotes:function () {
        var vm = this
        axios.get(' http://127.0.0.1:8000/travelnote/getalltravelnote/')
          .then(function (response) {
            vm.some = response.data
            console.log(vm.some)
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
  .active{
    border: rgba(34, 34, 34, 0.54) 1px solid;
    border-bottom: none;
  }
  body{
    position: fixed;
  }
  .nopadding{
    padding: 0;
  }
  .left{
    float:left;
  }
  .right {
    float: right;
  }
  /*右框架*/
  .rightcover{
    height: 240px!important;
    width: 340px!important;
    background-color: limegreen;
    border-radius: 10px 0 0 10px;

  }
  .rightcover img{
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 10px 0 0 10px;
    display: flex;
  }
  /*左框架*/
  .leftcover{
    height: 150px;
    width: 100%;
    background-color: orange;
    border-radius: 10px 10px 0 0 ;
    justify-content: space-between;
  }
  .leftcover img{
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 10px 10px 0 0 ;
  }
  /*基础框架*/
  .father{
    display: flex;
  }
  .boxleft{
    justify-content: space-between;
    width: 400px;
    height: 240px;
    background-color: cornflowerblue;
    border-radius: 10px;
    margin-top: 15px;
  }
  .boxright{
    justify-content: space-between;
    width: 557px;
    height: 240px;
    background-color: #ed7a7f;
    margin-left: 20px;
    border-radius: 10px;
    margin-top: 15px;

  }
  .post-window {
    height: auto;
    display: block;
    padding-top: 10px;
    margin-bottom: 20px;
  }
  /*******************/







  .post-window .nav-tabs > li > a {
    border-radius: 5px 5px 0 0;
  }

  .post-window ul li a:hover {
    color: white;
    background-color: #7eeda8;
  }

  .list-post {
    width: 100%;
    height: auto;
    padding: 0;
    padding-bottom: 15px;
  }

  .list-post > a {
    border-radius: 5px;
    margin-top: 10px;
    margin-left: 10px;
    height: 150px;
    background-color: white;
  }

  .list-post .item:hover {
    -webkit-box-shadow: inset 0 1px 0 rgba(255, 255, 255, .15), 0 1px 5px rgba(0, 0, 0, .075);
    box-shadow: inset 0 1px 0 rgba(255, 255, 255, .15), 0 1px 5px rgba(0, 0, 0, .075);
  }

  .hot-travel {
    min-height: 450px;
  }

  .new-post {
    min-height: 450px;
    display: none;
  }

  .new-strategys {
    min-height: 450px;
    display: none;
  }

  .content {
    width: 100%;

  }

  .box {
    max-width: 400px;
    max-height: 300px;
    min-width: 400px;
    min-height: 300px;
    padding: 0;
    margin-top: 13px;
    margin-right: 13px;
    border-radius: 4px !important;
  }

  .img:hover + .cover {
    display: block;
    height: 100%;
    transition: height 0.2s;
  }

  .user {
    border-radius: 4px 0 0 0;
    width: 75%;
    height: 20%;
    background-color: rgba(14, 13, 13, 0.31);
    padding: 5px 10px;
    filter: alpha(opacity=50);
    position: absolute;
    left: 0;
    z-index: 2;
  }

  .user img {
    float: left;
  }

  .user div {
    color: white;
    font-size: 13px;
    float: left;
    line-height: 20px;
    margin-left: 10px;
    overflow: hidden;
  }

  .title {
    border-radius: 0 0 0 4px;
    width: 75%;
    height: 30%;
    padding: 0 10px;
    background-color: rgba(14, 13, 13, 0.31);
    filter: alpha(opacity=50);
    position: absolute;
    top: 105px;
    left: 0;
    z-index: 2;
    overflow: hidden;
  }

  .title span {
    opacity: 1 !important;
    color: white;
    font-size: 15px;
    overflow: hidden;
  }

  .title2 {
    box-shadow: rgba(0, 0, 0, 0.25) 1px 1px 5px 3px;
  }

  .title2-left li:active {
    background-color: rgba(76, 174, 76, 0.75) !important;
    transition: background-color 0.3s;
    color: whitesmoke;
  }

  /*透明覆盖**********************************/
  .cover {
    width: 75%;
    height: 0;
    background-color: rgba(14, 13, 13, 0.76);
    filter: alpha(opacity=50);
    position: absolute;
    top: 0;
    left: 0;
    font-size: 14px;
    color: whitesmoke;
    overflow: hidden;
    z-index: 3;
    transition: height 0.1s;
    border-radius: 4px;
  }

  .cover:hover {
    display: block;
    height: 100%;
    transition: height 0.2s;
  }

  .cover p {
    margin: 15px;
  }

  .cover:active {

  }

  .item {
    padding: 0;
  }
  .stay {
    position: fixed;
    z-index: 4;
    left: 1203px;
    top: 400px;
  }

  .w-strategy {
    padding: 5px;
  }

  .text {
    border-radius: 0 4px 4px 0;
    background-color: white;
    height: 150px;
  }

  .text .num {
    text-align: center;
    color: #333333;
  }

  .good {
    height: 20px;
    width: 20px;
    margin: 5px 0;
    margin-left: 12.5px;
    background-size: cover;
    opacity: 1;
    background-image: url(../assets/images/zan.png);
  }

  .good:visited {
    background-size: cover;
    background-image: url("../assets/images/zan.png");
  }

  .look {
    height: 20px;
    width: 20px;
    /*margin: 5px;*/
    margin: 5px 0;
    margin-left: 12.5px;
    background-size: cover;
    background-image: url("../assets/images/浏览.png");
  }
  .city {
    height: 20px;
    width: 20px;
    margin: 5px 0;
    margin-left: 12.5px;
    background-size: cover;
    background-image: url("../assets/images/定位.png");
  }
</style>

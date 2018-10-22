<template>
  <div>
    <ul class="myfocus container-fluid">
      <li class="nav navbar navbar-nav col-md-4  card" style="contenteditable:true">
        <div class="col-md-3 collection " ref="abc" @click="showita($event)">游记收藏</div>
        <div class="col-md-3 collection" ref="def" @click="showita($event)">攻略收藏</div>
        <!--游记详情-->
        <div v-if="!this.showit">
          <div class="col-md-12" style="margin-top: 20px">
            <div class="col-md-4 content-img"><img src="../../assets/images/collection-img1.png" alt=""></div>
            <div class="col-md-8">
              <a href="">
                <h3 style="margin-top: 0;color: #fa0">岛屿来信,我想唱给你听
                  <button type="button" class="btn-collect">取消收藏</button>
                </h3>
              </a>

              <p style="color: #666">
                <img src="http://n3-q.mafengwo.net/s12/M00/ED/22/wKgED1vEm1GAJYGdAA4JRgRT65c86.jpeg?
                imageMogr2%2Fthumbnail%2F%21196x140r%2Fgravity%2FCenter%2Fcrop%2F%21196x140%2Fquality%2F90"
                     style="width: 16px;height: 16px">
                作者：梁雨甜
              </p>
              <p style="font-size: 14px;color: #666">
                不知从什么时候，在心底种下了这颗种子 我向往着白色沙滩躺椅旁的橘子汽水
                我期待着骑行在丛林的轻快节奏 我幻想着住在一个面朝大海的House，听潮起
                潮落，守望日出或等候日落 当然，这一切我希望是和你，一起 有人
              </p>
            </div>
          </div>
        </div>
        <!--攻略详情-->
        <div v-if="this.showit">
          <div class="col-md-12" style="margin-top: 20px">
            <div class="col-md-4 content-img"><img src="../../assets/images/collection-img2.png" alt=""></div>
            <div class="col-md-8">
              <a href="">
                <h3 style="margin-top:0;text-decoration: none;font-size: 18px">[马来亚-吉隆坡]
                  <button type="button" class="btn-collect" style="margin-left: 200px;color:#fa0">取消收藏</button>
                </h3>
              </a>

              <p style="color: #666"> 吉隆坡攻略大全...</p>
              <p>1.吉隆坡攻略路线..</p>
              <p>2.好吃的美食在哪里？？</p>
            </div>
          </div>
        </div>
      </li>
      <li class="nav navbar navbar-nav col-md-4"></li>
      <li class="nav navbar navbar-nav col-md-4"></li>
    </ul>
  </div>

</template>

<script>
  export default {
    name: 'MyFocus',
    // props:['user'],
    data() {

      return {
        showit: false,
      }
    },
    created() {

      // this.props.user = this.user

      // this.props.token = "123"
    },

    methods: {

      // 显示游记攻略
      showita: function (event) {
        var vm = this
        vm.showit = !vm.showit
        vm.$refs.abc.style.borderBottomColor = "white"
        vm.$refs.def.style.borderBottomColor = "white"
        event.currentTarget.style.borderBottomColor = "#fa0"
      },
      // 获取关注人信息
      getmessage: function () {
        var vm = this
        var id = sessionStorage.getItem("id")
        axios.get(' http://127.0.0.1:8000/user/myfocus/' + id + '/')
          .then(function (response) {
            vm.some = response.data
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
  ul, li {
    list-style: none;
  }

  .myfocus {
    width: 100%;
    height: 100%;
    align-items: center;
  }

  .card {
    border: rgba(0, 0, 0, 0.2) 1px solid;
    border-radius: 10px;
    box-shadow: rgba(0, 0, 0, 0.2) 0px 1px 10px 1px;
    padding: 10px 15px;
    width: 700px;
    margin-left: 15px;
    margin-top: 35px;
  }

  .collection {
    height: 35px;
    font-size: 17px;
    margin-top: 10px;
    margin-left: 95px;
    border-bottom: 2px white solid;
    text-align: center;

  }

  .collection-img img {
    background-repeat: no-repeat;
  }

  h3 a {
    font-size: 18px;
    color: #fa0;
  }

  .btn-collect {
    font-size: 12px;
    margin-left: 75px;
    line-height: 8px;
    margin-top: 2px;
    border: 0px;
    background: white;
  }

  p {
    margin-bottom: 0px;
  }

  a {
    /*font-weight: bold;*/
    color: darkgrey;
    text-decoration: none;
  }

</style>

<template>
  <div>

    <div id="set-bg-big">
      <!--名字-->
      <!--<h1 style="white-space: nowrap; overflow-wrap: normal;">无问南北西东，只愿你像风一样自由</h1>-->
    </div>

    <div class="container-fluid" style="height: 80px;border-bottom: 1px solid rgb(158,158,158)">
      <div class="col-md-3" id="user-head">
        <img width="120" height="120"
             src="http://n1-q.mafengwo.net/s11/M00/D1/0A/wKgBEFsGwmSAMQ_ZADZa-1o8WYQ95.jpeg?imageMogr2%2Fthumbnail%2F%21200x200r%2Fgravity%2FCenter%2Fcrop%2F%21200x200%2Fquality%2F90"
             alt="">
      </div>

      <div class="col-md-5" id="user-person">
        <strong>
          <a href="/u/87710821.html" target="_blank" class="per_name" title="采蘑菇的juju佩奇">采蘑菇的juju佩奇</a>
          <a href="/u/87710821.html" target="_blank" class="per_grade" title="LV.11">LV.11</a>
          <img src="http://images.mafengwo.net/images/home/tweet/btn_sfollow.gif" width="38" height="13" border="0"
               title="关注TA">
          <span class="now_time">2018-09-01 14:01</span>
          <span><i class="ico_view"></i>5754/44</span>
        </strong>
      </div>

      <!--收藏-->
      <div class="col-md-1" id="collect">
        <a @click="collecttravelnote" href="" rel="nofollow" title="收藏" class="collect_num"
           data-ctime="2018-09-01 14:01:56">
          <i></i><br>
          <span v-text="this.collect">136</span>收藏
        </a>
      </div>

      <!--点赞-->
      <div class="col-md-1">
        <a href="">
          <div @cilck="praisenum" class=" praise">
            <i></i> <br>
            <span v-text="this.praise">25</span>点赞
          </div>
        </a>
      </div>
    </div>

    <div contenteditable="true" id="write-notes-day">游记详情啥的.....</div>
  </div>
</template>

<script>
  export default {
    name: "DetailPages"
  }
</script>

<style scoped>
  body, div, dl, dt, dd, ul, ol, li, h1, h2, h3, h4, h5, h6, pre, code, form, fieldset, legend, input, button, textarea, p, blockquote, th, td {
    margin: 0;
    padding: 0;
    list-style: none;
  }
  #set-bg-big {
    background-image: url("../../assets/travelnote/set-bg-.png");
    width: 1400px;
    height: 500px;
    background-repeat: no-repeat;
  }

  /*头像*/
  #user-head img {
    border-radius: 50%;
    position: absolute;
    top: -60px;
    left: 45%;
    z-index: 88;
  }

  #user-person {
    width: 450px;
    height: 78px;
    border-right: 1px solid #d7d7d7;
    padding: 20px 0 0 150px;
    float: left;
  }

  /*个人信息*/
  a {
    background-color: transparent;
    text-decoration: none;
    color: #ff9d00;
    cursor: pointer;
  }

  a.per_name {
    color: #ff7200;
    font-size: 14px;
    font-weight: normal;
    margin-left: -45%;
  }

  a.per_grade {
    color: #ea3c1a;
    font-family: Verdana, Arial, Helvetica, STHeiti;
    font-size: 10px;
    font-weight: bold;
    text-decoration: none;
  }

  span.now_time {
    font-family: Verdana, Arial, Helvetica, STHeiti;
    margin-right: 10px;
    color: #acacac;
    display: inline;
    margin-left: 10px;
  }

  span i {
    width: 18px;
    height: 14px;
    display: inline-block;
    background: url(../../assets/travelnote/浏览.png);
    background-repeat: no-repeat;
    margin-right: 4px;
    vertical-align: -2px;
  }

  span {
    color: #acacac;
    font-size: 12px;
  }

  /*收藏*/
  a.collect_num i {
    width: 30px;
    height: 30px;
    display: inline-block;
    background: url("../../assets/travelnote/collect.png");
    margin-top: 15px;
    margin-left: 35px;
  }

  a.collect_num span {
    margin-left: 30px;
  }

  #collect {
    height: 80px;
    border-right: 1px solid #acacac
  }

  /*点赞*/
  .praise {
    height: 80px;
    border-right: 1px solid #acacac
  }

  .praise i {
    width: 30px;
    height: 30px;
    display: inline-block;
    background: url("../../assets/travelnote/zan.png");
    margin-top: 15px;
    margin-left: 35px;
  }

  .praise span {
    margin-left: 30px;
  }



  /*footer显示游记详情...*/
  #write-notes-day {
    width: 1000px;
    height: 400px;
    margin: auto;
    padding-left: 20px;
    font-size: 15px;
    border:1px solid rgb(158,158,158);
    border-top: none;
    border-bottom: none;
    outline: none;
  }
</style>

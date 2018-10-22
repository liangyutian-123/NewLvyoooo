<template>
  <div class="container-fluid" style="height: 600px">

    <div class="container-fluid" style="padding: 0px; margin: 0px ;height: 58px;border-bottom: 1px solid rgba(208,208,208,0.56) ">
      <div class="col-md-3" id="logo-img"></div>
      <div class="col-md-6 hidden-xs form-group search " style="margin-top: 11px">
        <input  type="search" id="search-bar-input" placeholder="搜索目的地">
      </div>

      <div class="col-md-3" id="user-img">
        <img src="http://n2-q.mafengwo.net/s12/M00/35/2C/wKgED1uqImOAAxCCAAAeJTVWYJU680.png?imageMogr2%2Fthumbnail%2F%2132x32r%2Fgravity%2FCenter%2Fcrop%2F%2132x32%2Fquality%2F90"
          height="32" width="32" alt="">
      </div>
    </div>

    <div class="nav-list">
      <ul class="ul-list">
        <li>全部</li>
        <li>目的地</li>
        <li>旅游攻略</li>
        <li>游记</li>
        <li>找人</li>
      </ul>
    </div>

    <div class="container" style="position: relative ; left: 8%">
      <!--景点介绍-->
      <div class="col-md-10" style="max-width: 55%">
        <h2 class="left">马拉西亚Malaylsa</h2>

        <div class="jieshao">
          <img src="../../assets/travelnote/malaixiya.png" alt="" calss="jingdian-img">

          <p>马来西亚是东南亚的国家之一，1957年8月31日独立。<br>
            马来西亚是一个由十三州和三个联邦直辖区组成的联邦体制国家，<br>
            首都为吉隆坡，政治中心位于布城，是东南亚国家联盟的创始国之一。<br>
            与此同时，马来西亚也是一个自...</p>
        </div>
      </div>

      <div class="col-md-10">
        <h2 class="left">马拉西亚Malaylsa</h2>

        <div class="jieshao">
          <img src="../../assets/travelnote/malaixiya.png" alt="" calss="jingdian-img">

          <p>马来西亚是东南亚的国家之一，1957年8月31日独立。<br>
            马来西亚是一个由十三州和三个联邦直辖区组成的联邦体制国家，<br>
            首都为吉隆坡，政治中心位于布城，是东南亚国家联盟的创始国之一。<br>
            与此同时，马来西亚也是一个自...</p>
        </div>
      </div>


      <!--侧边栏-->
      <div class="col-md-2">
        <div id="right">
          <h2><span style="margin-left: 20px">马来西亚热门推荐景点</span></h2>
          <div class="col-md-4 web-side-img"></div>
          <div class="col-md-4 web-side-img"></div>
          <div class="col-md-4 web-side-img"></div>
          <br>
          <div class="col-md-4 web-side-img"></div>
          <div class="col-md-4 web-side-img"></div>
          <div class="col-md-4 web-side-img"></div>
          <br>
          <div class="col-md-4 web-side-img"></div>
          <div class="col-md-4 web-side-img"></div>
          <div class="col-md-4 web-side-img"></div>
        </div>
      </div>
      <!--旅游攻略-->
      <div class="col-md-10">
        <h2 class="left">马拉西亚旅游攻略</h2>

        <div class="jieshao">
          <img src="../../assets/travelnote/malaixi2.png" alt="" class="jingdian-img">

          <p>马来西亚是东南亚的国家之一，1957年8月31日独立。<br>
            马来西亚是一个由十三州和三个联邦直辖区组成的联邦体制国家，<br>
            首都为吉隆坡，政治中心位于布城，是东南亚国家联盟的创始国之一。<br>
            与此同时，马来西亚也是一个自...</p>
        </div>
      </div>

      <div class="col-md-10">
        <h2 class="left">马拉西亚旅游攻略</h2>
        <div class="jieshao">
          <img src="../../assets/travelnote/malaixi2.png" alt="" class="jingdian-img">
          <p>马来西亚是东南亚的国家之一，1957年8月31日独立。<br>
            马来西亚是一个由十三州和三个联邦直辖区组成的联邦体制国家，<br>
            首都为吉隆坡，政治中心位于布城，是东南亚国家联盟的创始国之一。<br>
            与此同时，马来西亚也是一个自...</p>
        </div>
      </div>
    </div>

    <div class="footer">addfaff</div>
  </div>

</template>

<script>
  export default {
    name: "SearchMain"
  }
</script>

<style scoped>
  body, div, dl, dt, dd, ul, ol, li, h1, h2, h3, h4, h5, h6, pre, code, form, fieldset, legend, input, button, textarea, p, blockquote, th, td {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  /*导航*/
  .container-fluid {
    height: 58px;
    /*border-bottom: solid 1px #9e9e9e;*/
  }

  #logo-img {
    background-image: url("../../assets/travelnote/logoweight.png");
    height: 40px;
    width: 150px;
    background-repeat: no-repeat;
    margin-left: 100px;
    margin-top: 5px;
  }

  #search-bar-input {
    border-top-right-radius: 5px;
    border-top-left-radius: 5px;
    border-bottom-right-radius: 5px;
    border-bottom-left-radius: 5px;
    background-color: #fafafa;
    outline-style: none;
    width: 450px;
    height: 30px;
    -webkit-appearance: none;
    -webkit-user-select: text;
    outline-color: transparent;
    box-shadow: none;
    border: 1px solid #7bcc57;
    background: url("../../assets/strategy/search22.png");
    background-position: 95%;
    background-repeat: no-repeat;
    margin-left: 10px;
    margin-top: 2px;
    padding-left: 20px;
  }

  #user-img img {
    vertical-align: middle;
    border-radius: 50%;
    margin-top: 15px;
    margin-left: 240px;
  }
  #user-img img:hover {
    vertical-align: middle;
    border-radius: 50%;
    margin-top: 15px;
    margin-left: 240px;
    border:3px solid #7bcc57 ;
  }

  /*-----------------------------*/
  #user a {
    color: #3f9f5f;
    text-decoration: none;
  }

  .container-fluid .nav-list {
    float: left;
    width: 100%;
    height: 50px;
    background: #fafafa;
  }

  .container-fluid .nav-list .ul-list {
    width: 1200px;
    height: 50px;
    margin: auto;
  }

  .container-fluid .nav-list .ul-list li {
    float: left;
    height: 40px;
    font-size: 15px;
    margin-top: 15px;
    color: #666;
    padding: 0 20px;
    margin-left: 15px;
  }

  .container {
    height: 1000px;
    margin-top: 30px;
    float: left;
  }

  .left {
    width: 600px;
    height: 30px;
    float: left;
    font-size: 18px;
    font-weight: bold;
    color: #333 !important;
    border-bottom: 1px solid #d0d0d0;
    margin-bottom: 10px;
    margin-top: 15px;
  }

  .jieshao {
    float: left;
    width: 600px;
    height: 110px;
  }

  .jingdian-img {
    margin-top: 10px;
    margin-left: 10px;
  }

  p {
    display: block;
    float: right;
    font-size: 13px;
    margin-top: 10px;
  }

  #right {
    width: 380px;
    height: 400px;
    border: 1px solid #f4f4f4;
    box-shadow: 0 0 7px rgba(0, 0, 0, 0.13);
    overflow: hidden;
    border-radius: 2px;
    margin-top: -150px;
    margin-left: -150px;
  }

  h2 {
    font-size: 18px;
    line-height: 30px;
    font-weight: bold;
    color: #333 !important;
    margin-top: 5px;
    margin-left: 4px;
  }

  .web-side-img {
    background-image: url("../../assets/travelnote/webside-img.png");
    width: 90px;
    height: 90px;
    border: 0;
    vertical-align: middle;
    margin-left: 25px;
    margin-top: 20px;
  }

  .footer {
    width: 100%;
    height: 150px;
    background: #3c3c3c;
    float: left;
  }
</style>

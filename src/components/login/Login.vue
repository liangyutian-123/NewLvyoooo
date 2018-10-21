<template>
  <div class="container">
    <div class="logo">
      <div class="logoimg"></div>
    </div>


    <div class="land">
      <div class="numberland">登录</div>
      <div class="lineland"></div>
      <div class="landexplain">旅由网将实行 <a href="#">手机绑定实名制的说明</a></div>
      <input type="text" id="telephone" placeholder="请输入手机号" maxlength="11" v-model="telephone">
      <div class="interval0">
        <div class="interval0-1" v-if="tel_correct">手机号不合法</div>
      </div>
      <input type="password" id="password" placeholder="密码" maxlength="40" v-model="password">
      <div class="interval1"><a href="#">忘记密码</a>
        <div class="interval1-2" v-if="psd_correct">密码长度小于六位</div>
      </div>
      <button class="btn" @click="login">登录</button>

      <div class="lowerexplain">
        <div class="register">没有账号？
          <router-link to="/regist"><a href="2_regist.html">立即注册</a></router-link>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
  import axios from 'axios';

  export default {
    name: "Login",
    data: function () {
      return {
        telephone: '',
        password: '',
        tel_correct: false,
        psd_correct: false
      }
    },
    created: function () {
      this.debouncedvertifyTel = _.debounce(this.Tel, 1000)
      this.debouncedvertifyPsd = _.debounce(this.Psd, 1000)
    },
    methods: {
      Tel: function () {
        if (!this.telephone) {
          this.tel_correct = false
        } else if (!(/^1[34578]\d{9}$/.test(this.telephone))) {
          this.tel_correct = true
        }
        else {
          this.tel_correct = false
        }
      },
      Psd: function () {
        if (!this.telephone) {
          this.psd_correct = false
        } else if (this.password.length < 6) {
          this.psd_correct = true
        }
        else {
          this.psd_correct = false
        }
      },
      //发送ajax请求
      login: function () {
        var that = this
        alert("login")
        axios.post('http://127.0.0.1:8000/user/login/', {'telephone': that.telephone, 'password': that.password})
          .then(function (response) {
            if (response.data.length) {
              // sessionStorage.setItem("telephone",response.data[0]["telephone"])
            }
            console.log(response.data)
          })
          .catch(function (err) {
            if (err.response) {
              console.log(err.response)
            }
          })
      }
    },
    watch: {
      telephone: function (newtel) {
        this.debouncedvertifyTel();
      },
      password: function () {
        this.debouncedvertifyPsd();
      }
    }


  }
</script>

<style scoped>
  body, div, dl, dt, dd, ul, ol, li, h1, h2, h3, h4, h5, h6, pre, code, form, fieldset, legend, input, button, textarea, p, blockquote, th, td {
    margin: 0;
    padding: 0;
  }

  .container {
    width: 100%;
    height: 641px;
    background: url("https://images.mafengwo.net/images/signup/wallpaper/37.jpg");
    background-size: 100% 641px;
  }
  /*logo*/
  .container .logo {
    width: 380px;
    height: 60px;
    position: relative;
    left: 50%;
    transform: translate(-50%, 0);
    top: 80px;
  }

  .container .logo .logoimg {
    width: 300px;
    height: 60px;
    background-image: url("../../assets/travelnote/logoweight.png");
    background-repeat: no-repeat;
    margin-left: 115px;
  }

  .container .land {
    width: 380px;
    height: 350px;
    background: white;
    position: relative;
    left: 50%;
    transform: translate(-50%, 0);
    top: 110px;

  }

  .container .land .numberland {
    width: 165px;
    height: 60px;
    margin: auto;
    font-size: 20px;
    color: #3f9f5f;
    line-height: 60px;
    text-align: center;
  }

  .container .land .lineland {
    width: 330px;
    height: 1px;
    background: rgba(29, 14, 14, 0.3);
    margin-left: 25px;
  }

  .container .land .landexplain {
    width: 270px;
    height: 50px;
    margin-left: 25px;
    font-size: 14px;
    color: rgba(0, 0, 0, 0.51);
    line-height: 50px;
    text-align: left;
  }

  .container .land .landexplain a {
    text-decoration: none;
    color: #3f9f5f;
  }

  .container .land .landexplain a:hover {
    text-decoration: underline;
  }

  .container .land input {
    width: 330px;
    height: 40px;
    outline: none;
    box-sizing: border-box;
    font-size: 14px;
    padding-left: 5px;
    margin-left: 25px;

  }

  .container .land .interval0 {
    width: 330px;
    height: 30px;
    margin-left: 25px;

  }

  .container .land .interval0 .interval0-1 {
    width: 330px;
    height: 30px;
    font-size: 12px;
    color: red;
  }

  .container .land .interval1 {
    width: 330px;
    height: 30px;
    margin-left: 25px;
    line-height: 30px;

  }

  .container .land .interval1 a {
    float: right;
    text-decoration: none;
    font-size: 12px;
    color: rgba(0, 0, 0, 0.51);
  }

  .container .land .interval1 a:hover {
    color: rgba(0, 128, 0, 0.5);
  }

  .container .land .interval1 .interval1-2 {
    width: 330px;
    height: 30px;
    font-size: 12px;
    color: red;
  }

  .container .land .btn {
    width: 330px;
    height: 36px;
    margin-left: 25px;
    font-size: 16px;
    color: white;
    background: #3f9f5f;
    outline: none;
    border: 0;
    border-radius: 3px;
  }

  .container .land .btn:hover {
    background: rgba(63, 159, 95, 0.61);
  }

  .container .land .lowerexplain {
    width: 330px;
    height: 40px;
    margin-left: 25px;
  }

  .container .land .lowerexplain .register {
    float: left;
    width: 175px;
    height: 20px;
    font-size: 14px;
    margin-left: 0px;
    margin-top: 10px;
    line-height: 20px;
    color: rgba(0, 0, 0, 0.5);
  }

  .container .land .lowerexplain .register a {
    text-decoration: none;
    font-size: 14px;
    color: rgba(0, 128, 0, 0.5);
  }

  .container .land .lowerexplain .register a:hover {
    text-decoration: underline;
  }


</style>

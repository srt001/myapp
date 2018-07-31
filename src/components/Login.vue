<template>
  <div id="login">
      <div class="container login-content">
            <section id="content">
                <form>
                    <h1>ログイン</h1>
                    <div>
                        <input type="text" placeholder="ユーザーＩＤ" id="username" v-model="userID"/>
                    </div>
                    <div>
                        <input type="password" placeholder="パスワード" id="password" v-model="txtPass" />
                    </div>
                    <div class="btn">
                        <button id="btnLogin" class="button button-positive" v-on:click="login">ログイン</button>
                        <button id="btnReset" class="button button-positive" v-on:click="resetForm">クリア</button>
                    </div>   
                    <div class="messages">
                        <span id="messages"></span>
                    </div>
                </form><!-- form -->
            </section><!-- content -->
        </div><!-- container -->
  </div>
</template>

<script>
import axios from "axios";
import Qs from "qs";
// Vue.prototype.axios=axios;

export default {
  name: "login",
  data() {
    return {
      userID: "",
      txtPass: ""
    };
  },
  //从父组件传值到子组件
  //props: ['logo']
  methods: {
    login: function() {
      // `this` 在方法里指向当前 Vue 实例
      console.info("login");
      console.info("userId: " + this.userID);
      console.info("txtPass: " + this.txtPass);
      //http://192.168.108.75:8080/ISCPayManagement/authenticate.do
      //http://192.168.108.75:8080/ISCPayManagement/authenticate.do;
      var url = "api/authenticate.do";

      let data = {
        userID: "200007",
        txtPass: "123456"
      };

        axios
          .post(
            url,
            {
              'userID': this.userID,
              'txtPass': this.txtPass
            },
            {
              headers: {
                "Content-type": "application/json"
            //   "Content-type": "application/x-www-form-urlencoded"
              }
            }
          )
          .then(function(response) {
              console.log("登録成功");
              console.log(response);
          })
          .catch(function(error) {
              console.log("登録失敗");
              console.log(error);
          });

    //   axios({
    //     // headers: {
    //     //     // "Content-type": "application/json"
    //     //   "Content-type": "application/x-www-form-urlencoded"
    //     // },
    //     method: "post",
    //     url: "api/authenticate.do",
    //     data: Qs.stringify(data)
    //   });

      // axios.post({
      //   method: 'post',
      //   baseURL: 'api',
      //   url: 'authenticate.do',
      //   data: {
      //     userID: this.userID,
      //     txtPass: this.txtPass
      //   }
      // }).then(function (response) {
      //     console.log(response);
      //   })
      //   .catch(function (error) {
      //     console.log(error);
      //   });
    },

    resetForm: function() {
      // `this` 在方法里指向当前 Vue 实例
      console.info("resetForm");
      this.staffID = "";
      this.password = "";
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import "../assets/css/login.css";

#bottomNav {
  display: flex;
  width: 100%;
  height: 3rem;
  line-height: 3rem;
  padding: 0.5rem 0;
  text-align: center;
  border-top: 1px solid #999999;
  position: fixed;
  left: 0;
  bottom: 0;
  background-color: aliceblue;
}

.tab {
  flex: 1;
  text-align: center;
  border-right: 1px solid #999999;
}
</style>
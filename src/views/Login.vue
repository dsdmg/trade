<template>
<div>
   <div class="title-bar">
      <span>密码登录</span>
      <div class="right">
        <img @click="close" src="../assets/icon_close.png"  draggable="false">
        <img @click="minimize" src="../assets/icon_minimize.png"  draggable="false">
      </div>
    </div>
    <div class="main">
    <div class="avatar">
      <el-avatar :size="60" src="https://cube.elemecdn.com/0/88/03b0d39583f48206768a7534e55bcpng.png"></el-avatar>
    </div>
    <div class="item">
      <el-input placeholder="请输入账号" v-model="account" clearable prefix-icon="el-icon-user"></el-input>
    </div>
    <div class="item">
      <el-input placeholder="请输入密码" v-model="password" show-password prefix-icon="el-icon-lock"></el-input>
    </div>
    <div class="item">
      <el-button type="primary" round @click="login">登录</el-button>
    </div>
  </div>
</div>
</template>
<script>
const { ipcRenderer } = require('electron')
export default {
  name: 'Login',
  data () {
    return {
      account: '',
      password: ''
    }
  },
  methods: {
    minimize () {
      ipcRenderer.send('minimize')
    },
    close () {
      ipcRenderer.send('close')
    },
    login () {
      if (this.account === 'admin' && this.password === '123456') {
        this.$router.push('Home')
      } else {
        this.$message.error('用户名或密码错误')
      }
    }
  }
}
</script>
<style scoped>
.main{
    margin-left:30px
}

.avatar{
    margin-top:40px;
    margin-right:30px
}

button{
    width:100%
}

.item{
    margin-top:20px;
    margin-right:30px
}
.title-bar{
  height:50px;
  line-height:50px;
  background-color:#409EFF;
  -webkit-app-region:drag/*  可拖动 */
}

.title-bar .right{
    position: absolute;
    top: 0px;
    right: 0px;
    -webkit-app-region: no-drag  /* // 不可拖动 */

}

.title-bar span{
  color:white;
  display: inline;
  text-align: center;
  font-size: 18px
}

.title-bar .right img{
  width:20px;
  height:20px;
  float:right;
  margin-top :15px;
  margin-right :15px
}

</style>

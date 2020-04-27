<template>
  <div class="top-bar">
      <div class="top-left">
        <img :src="logoImg" draggable="false">
    </div>
      <div class="top-right">
        <img @click="minimize" :src="minImg" draggable="false">
        <img @click="close" :src="closeImg" draggable="false">
    </div>
  </div>
</template>

<script>
const { ipcRenderer } = require('electron')
export default {
  name: 'Titelbar',
  data () {
    return {
      logoImg: require('../assets/logo.png'),
      minImg: require('../assets/icon_minimize.png'),
      closeImg: require('../assets/icon_close.png')
    }
  },
  methods: {
    minimize () {
      ipcRenderer.send('minimize')
    },
    close () {
      ipcRenderer.send('close')
    }
  }

}
</script>

<style>
.top-left img{
  width: 40px;
  height: 40px;
  margin-left: -10px;
  -webkit-app-region: no-drag
}
.top-right img{
  width: 40px;
  height: 40px;
  margin-right: 10px;
  -webkit-app-region: no-drag
}
.top-bar{
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    -webkit-app-region: drag
}
/* .el-aside .right{

}
.el-aside .right img{

  margin-top: 2px;

} */
</style>

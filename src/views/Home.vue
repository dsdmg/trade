<template>

<el-container class="home-container">
  <el-header>
    <Titelbar></Titelbar>
  </el-header>
  <el-container>
    <el-aside width="200px">
      <Siderbar></Siderbar>
    </el-aside>
    <el-main>
      <SimulantBtn :imgList="imgList" @MainbtnClick="MainbtnClick"/>
      <!-- <router-view></router-view> -->
      </el-main>
  </el-container>
</el-container>

</template>
<script>
import SimulantBtn from '../components/SimulantBtn.vue'
import Siderbar from '../components/Sidebar.vue'
import Titelbar from '../components/Titelbar.vue'
const { ipcRenderer } = require('electron')
export default {
  name: 'Home',
  data () {
    return {
      imgList: [{ name: '录音机', imgpath: require('../assets/icos/录制.png') },
        { name: '时钟', imgpath: require('../assets/icos/时钟.png') },
        { name: '微信', imgpath: require('../assets/icos/微信.png') },
        { name: '浏览器', imgpath: require('../assets/icos/浏览器.png') },
        { name: '电话', imgpath: require('../assets/icos/电话 (1).png') },
        { name: '相册', imgpath: require('../assets/icos/相册.png') },
        { name: '相机', imgpath: require('../assets/icos/相机.png') },
        { name: '通讯录', imgpath: require('../assets/icos/通讯录.png') },
        { name: 'youtube', imgpath: require('../assets/icos/youtube.png') },
        { name: 'facebook', imgpath: require('../assets/icos/facebook.png') },
        { name: '哔哩哔哩', imgpath: require('../assets/icos/BILIBILI_LOGO (1).png') },
        { name: 'QQ', imgpath: require('../assets/icos/QQ (1).png') },
        { name: '短信', imgpath: require('../assets/icos/短信.png') },
        { name: '日历', imgpath: require('../assets/icos/日历.png') }]
    }
  },
  components: {
    SimulantBtn,
    Siderbar,
    Titelbar
  },
  mounted () {
    this.changeWindowSize()
  },
  methods: {
    MainbtnClick (item) {
      const h = this.$createElement

      this.$notify({
        title: '祝楠昊',
        message: h('i', { style: 'color: teal' }, '祝楠昊祝楠昊祝楠昊祝楠昊祝楠昊祝楠昊')
      })
    },
    changeWindowSize () {
      ipcRenderer.send('changWindowSize')
    }
  }
}
</script>
<style  scoped>
.home-container{
  height: 100%;
}
.el-header{
  background-color: #bfbebe;
}
.el-aside{
  background-color:#efeeee;
}
</style>

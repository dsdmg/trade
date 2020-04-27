<template>
  <div class="container">
    <div class="box" v-for="item in imgList" v-bind:key="item.name">
      <div class="img"  @click="btnClick(item)" >
        <img v-bind:src="item.imgpath" draggable="false">
       </div>
      <p>{{item.name}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SimulantBtn',
  props: {
    imgList: {
      type: Array
    }
  },
  methods: {
    btnClick (item) {
      this.$emit('MainbtnClick', item)
    }
  }
}
</script>

<style>
.container{
    display: flex;
    justify-content: space-evenly;
    flex-wrap: wrap;
    align-items: center;
    background-color: #efeeee;
     /* -webkit-app-region:drag */
     /*  可拖动 */
}
.container .box{
    display: flex;
    user-select: none;
    justify-content: space-around;
    flex-direction: column;
    align-items: center;
    align-content: center;
    width: 100px;
    height: 100%;
    margin: 20px;
}
.container .box .img{
    width: 100px;
    height: 100px;
    box-shadow: 18px 18px 30px rgba(0, 0, 0, 0.1),
    -18px -18px 30px rgba(255, 255, 255, 1);
    border-radius: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
     background-color: #efeeee;
    transition: box-shadow .2s ease-out;
    position: relative;
    -webkit-app-region: no-drag  /* // 不可拖动 */
}

.container .box .img  img{
    width: 60px;
    transition: width 0.2s ease-out;
}
.container .box p{
    color: slategrey;
}
.container .box .img:active{
    box-shadow: 0px 0px 0px rgba(0, 0, 0, 0.2),
    0px 0px 0px rgba(255, 255, 255, 0.8),
    inset 18px 18px 30px rgba(0, 0, 0, 0.1),
    inset -18px -18px 30px rgba(255, 255, 255, 1);
    transition: box-shadow .2s ease-out;
}
.container .box .img:active img{
    width: 58px;
    transition: width 0.2s ease-out;
}
</style>

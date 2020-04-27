<template>
 <el-menu
      default-active="2"
      class="el-menu-vertical-demo"
      active-text-color="#1296db"
      background-color="#efeeee"
     >
     <!-- -->
<!-- text-color="#fff" -->
      <el-submenu index="1">
        <template slot="title">
          <i class="el-icon-document"></i>
          <span slot="title">活动项目</span>
        </template>
        <el-menu-item index="1-1">主页面</el-menu-item>
        <el-menu-item index="1-2">合同登记</el-menu-item>
      </el-submenu>

      <el-submenu index="2">
        <template slot="title">
         <i class="el-icon-bell"></i>
        <span slot="title">代办项目</span>
        </template>

        <el-menu-item index="2-1">合同审核</el-menu-item>
      </el-submenu>

      <el-submenu index="3">
        <template slot="title">
          <i class="el-icon-menu"></i>
          <span slot="title">全部类目</span>
          <span></span>
        </template>
        <el-menu-item-group>
          <template slot="title">分组一</template>
          <el-menu-item index="3-1">选项1</el-menu-item>
          <el-menu-item index="3-2">选项2</el-menu-item>
        </el-menu-item-group>
        <el-menu-item-group title="分组2">
          <el-menu-item index="3-3">选项3</el-menu-item>
        </el-menu-item-group>
      </el-submenu>
    </el-menu>
</template>

<script>
export default {
  name: 'Sidebar'
}
</script>

<style>
.el-menu{
  text-align: left;

  /* ;
  ; */
}
</style>

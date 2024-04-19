<template>
  <div class="aside" style="height: 100%; width: 100%">
    <el-row class="tac" style="height: 100%; width: 100%">
      <el-col :span="12" style="height: 100%; width: 100%">
        <el-menu
          default-active="this.$route.path"
          router
          class="el-menu-vertical-demo"
          @open="handleOpen"
          @close="handleClose"
          background-color="#545c64"
          text-color="#fff"
          active-text-color="#ffd04b"
          style="height: 100%; width: 100%"
        >
          <el-submenu index="/pagesOne">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span>数据集介绍</span>
            </template>
            <el-menu-item-group>
              <el-menu-item index="/">UCR</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="1-4">
              <template slot="title">UEA</template>
              <el-menu-item index="1-4-1">类型一</el-menu-item>
              <el-menu-item index="1-4-1">类型二</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-menu-item index="/pagesTwo">
            <i class="el-icon-menu"></i>
            <span slot="title">数据集可视化</span>
          </el-menu-item>
          <el-menu-item index="/pagesOne">
            <i class="el-icon-menu"></i>
            <span slot="title">实验结果可视化</span>
          </el-menu-item>
          <el-submenu index="/pagesTwo">
            <template slot="title">
              <i class="el-icon-link"></i>
              <span>相关网址</span>
            </template>
            <el-menu-item index="1-4-1" @click="jump"
              >时间序列分类网站</el-menu-item
            >
          </el-submenu>
          <el-menu-item index="/pagesTwo">
            <i class="el-icon-setting"></i>
            <span slot="title">设置</span>
          </el-menu-item>
        </el-menu>
      </el-col>
    </el-row>
  </div>
</template>
<script>
export default {
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    },
    jump() {
      window.open("https://www.timeseriesclassification.com", "_blank");
    },
  },
};
</script>

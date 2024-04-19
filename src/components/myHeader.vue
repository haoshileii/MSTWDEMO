<template>
  <el-header>
    <div>
      <img src="..\src\assets\logo3.png" alt="logo" />
      <span>多变量时间序列可视化系统</span>
    </div>
    <el-button type="info" @click="logout">退出</el-button>
  </el-header>
</template>
<script>
export default {
  methods: {
    goBack() {
      console.log("go back");
    },
  },
};
</script>
<style lang="less" scoped>
.home-container {
  height: 100%;
}
.el-header {
  background-color: #373d41;
  display: flex;
  justify-content: space-between;
  padding-left: 0; // 去掉图标左边缝隙
  align-items: center; // 按钮上下居中
  color: #fff;
  font-size: 20px;
  > div {
    // 文本纵向居中对齐
    display: flex;
    align-items: center;
    span {
      // 文本和图标之间间距
      margin-left: 15px;
    }
  }
  img {
    width: 61px;
    height: 61px;
  }
}
.el-asid {
  background-color: #333744;
}
.el-main {
  background-color: #eaedf1;
}
</style>

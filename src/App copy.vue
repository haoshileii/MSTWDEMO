<template>
  <div class="full-screen">
    <el-container class="home-container">
      <!--头部  -->
      <el-header>
        <div>
          <!-- <img
            src="..\src\assets\logo3.png"
            class="round-image"
            alt="logo"
            width="50px"
            height="60px"
            border-radius="50%"
            object-fit="cover"
          /> -->
          <span>多变量时间序列数据可视化系统</span>
        </div>
        <!-- 退出按钮 -->
        <el-button type="info" @click="logout">退出</el-button>
      </el-header>
      <!-- 页面主体区  嵌套容器  包裹 Aside与Main -->
      <el-container>
        <el-row class="tac">
          <el-col :span="12">
            <el-menu
              default-active="2"
              class="el-menu-vertical-demo"
              @open="handleOpen"
              @close="handleClose"
              background-color="#545c64"
              text-color="#fff"
              active-text-color="#ffd04b"
            >
              <el-submenu index="1">
                <template slot="title">
                  <i class="el-icon-location"></i>
                  <span>导航一</span>
                </template>
                <el-menu-item-group>
                  <template slot="title">分组一</template>
                  <el-menu-item index="1-1">选项1</el-menu-item>
                  <el-menu-item index="1-2">选项2</el-menu-item>
                </el-menu-item-group>
                <el-menu-item-group title="分组2">
                  <el-menu-item index="1-3">选项3</el-menu-item>
                </el-menu-item-group>
                <el-submenu index="1-4">
                  <template slot="title">选项4</template>
                  <el-menu-item index="1-4-1">选项1</el-menu-item>
                </el-submenu>
              </el-submenu>
              <el-menu-item index="2">
                <i class="el-icon-menu"></i>
                <span slot="title">导航二</span>
              </el-menu-item>
              <el-submenu index="3">
                <template slot="title">
                  <i class="el-icon-link"></i>
                  <span>相关网址</span>
                </template>
                <el-menu-item index="1-4-1" @click="jump"
                  >时间序列分类网站</el-menu-item
                >
              </el-submenu>
              <el-menu-item index="4">
                <i class="el-icon-setting"></i>
                <span slot="title">导航四</span>
              </el-menu-item>
            </el-menu>
          </el-col>
        </el-row>
        <el-main>Main</el-main>
      </el-container>
    </el-container>
  </div>
</template>
<script>
export default {
  name: "App",
  data() {
    return {
      isCollapse: true,
    };
  },
  methods: {
    // 退出操作
    logout() {
      // 清空token
      window.sessionStorage.clear();
      //  将登录页面转入到登录界面
      this.$router.push("/login");
    },
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
<style scoped lang="less">
// 标签的名字就是类的名字
.full-screen {
  height: 100vh; /* 视口高度 */
  width: 100vw; /* 视口宽度 */
}
.el-container {
  height: 100%;
}
.el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 200px;
  min-height: 400px;
}
.home-container {
  height: 100%;
}
.el-header {
  background-color: #545c64;
  display: flex;
  justify-content: space-between;
  padding-left: 0px;
  //  居中
  align-items: center;
  //  文本颜色
  color: #fff;
  // 文字大小
  font-size: 20px;
  // 给header中嵌套的div进行样式改造
  // 子代选择器
  > div {
    display: flex;
    //   纵向居中
    align-items: center;
    //   在给div中的span改造样式
    > span {
      margin-left: 20px;
    }
  }
}
.el-aside {
  background-color: #333744;
}
.el-main {
  background-color: #eaedf1;
  height: 100%;
}
</style>

<template>
  <el-container>
    <el-aside width="200px">
      <div class="title">阿里巴巴</div>
      <el-menu
        default-active="1"
        class="el-menu-vertical-demo"
        background-color="#545c64"
        text-color="#fff"
        active-text-color="#ffd04b"
      >
        <el-menu-item
          index="1"
          @click="$router.push('/postList').catch(() => {})"
        >
          <i class="el-icon-menu"></i>
          <span slot="title">文章列表</span>
        </el-menu-item>
        <el-menu-item
          index="2"
          @click="$router.push('/editPost').catch(() => {})"
        >
          <i class="el-icon-setting"></i>
          <span slot="title">发布文章</span>
        </el-menu-item>
      </el-menu>
    </el-aside>
    <el-container>
      <el-header>
        <div class="userInfo">
          <img class="avatar" src="../assets/默认头像.png" />
          <div class="name">可以吗</div>
          <div class="logout">退出</div>
        </div>
      </el-header>
      <el-main>
        <router-view />
      </el-main>
    </el-container>
  </el-container>
</template>

<script>
export default {};
</script>

<style lang="less" scoped>
.el-header {
  background-color: #555;
  color: #333;
  text-align: center;
  line-height: 60px;
  .userInfo {
    line-height: 60px;
    float: right;
    -webkit-user-select: none;
    .avatar {
      float: left;
      width: 46px;
      height: 46px;
      border-radius: 23px;
      margin-top: 6px;
    }
    .name {
      font-size: 16px;
      float: left;
      margin-left: 6px;
      color: #fff;
    }
    .logout {
      margin-left: 14px;
      font-size: 16px;
      float: left;
      color: #fff;
      cursor: pointer;
      transition: all 0.2s;
      &:hover {
        color: #ffd04b;
      }
    }
  }
}

.el-aside {
  background-color: #333;
  color: #fff;
  text-align: center;
  height: 100vh;
  .title {
    line-height: 60px;
    font-weight: 700;
    font-size: 20px;
  }
  .el-menu-vertical-demo {
    border: 0;
  }
}

.el-main {
  background-color: #e9eef3;
  color: #333;
  text-align: center;
  line-height: 160px;
}

body > .el-container {
  margin-bottom: 40px;
}

.el-container:nth-child(5) .el-aside,
.el-container:nth-child(6) .el-aside {
  line-height: 260px;
}

.el-container:nth-child(7) .el-aside {
  line-height: 320px;
}
</style>
<template>
  <el-row type="flex" justify="center" align="middle" class="login">
    <el-form label-width="80px">
      <el-form-item label="用户名">
        <el-input v-model="form.username"></el-input>
      </el-form-item>
      <el-form-item label="密码">
        <el-input v-model="form.password" type="password"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="login">登录</el-button>
        <el-button @click="reset">重置</el-button>
      </el-form-item>
    </el-form>
  </el-row>
</template>

<script>
export default {
  data() {
    return {
      form: {
        username: "",
        password: "",
      },
    };
  },
  methods: {
    login() {
      this.$axios({
        method: "post",
        url: "/login",
        data: this.form,
      }).then((res) => {
        if (res.data.message == "登录成功") {
          localStorage.setItem("token", res.data.data.token);
          this.$message({
            message: "登录成功",
            type: "success",
          });
          this.$router.push("/");
        } else {
          this.$message.error("账号是10086,密码是123哦");
        }
      });
    },
    reset() {
      this.form.username = "";
      this.form.password = "";
    },
  },
};
</script>

<style lang="less" scoped>
.login {
  height: 100vh;
  background-color: #e4e4e4;
}
</style>
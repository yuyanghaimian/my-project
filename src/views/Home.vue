<template>
  <div>
    <el-container class="container">
      <el-header class="header">
        <!-- 头部 -->
        <el-header class="header">
          <el-row>
            <el-row>
              <el-col :span="4">
                <div class="grid-content bg-purple">
                  <img src="@/assets/logo.png" alt>
                </div>
              </el-col>
              <el-col :span="19" class="middle">
                <h2>电商后台管理系统</h2>
              </el-col>
              <el-col :span="1">
                <a href="#" class="loginout" @click="handleOut">退出</a>
              </el-col>
            </el-row>
          </el-row>
        </el-header>
      </el-header>
      <el-container>
        <el-aside class="aside" width="200px">
          <!-- 侧边栏 -->
          <el-aside class="aside" width="200px">
            <el-menu default-active="2-1" class="menu" :unique-opened="true" :router="true">
              <!-- 用户管理-->
              <el-submenu index="1">
                <template slot="title">
                  <i class="el-icon-location"></i>
                  <span>用户管理</span>
                </template>
                <el-menu-item index="/user">
                  <i class="el-icon-menu"></i>
                  用户列表
                </el-menu-item>
              </el-submenu>
              <!-- 权限管理-->
              <el-submenu index="2">
                <template slot="title">
                  <i class="el-icon-location"></i>
                  <span>权限管理</span>
                </template>
                <el-menu-item index="/roles">
                  <i class="el-icon-menu"></i>
                  角色列表
                </el-menu-item>
                <el-menu-item index="/rights">
                  <i class="el-icon-menu"></i>
                  权限列表
                </el-menu-item>
              </el-submenu>
              <!-- 商品管理-->
              <el-submenu index="3">
                <template slot="title">
                  <i class="el-icon-location"></i>
                  <span>商品管理</span>
                </template>
                <el-menu-item index="3-1">
                  <i class="el-icon-menu"></i>
                  商品列表
                </el-menu-item>
                <el-menu-item index="3-1">
                  <i class="el-icon-menu"></i>
                  分类参数
                </el-menu-item>
                <el-menu-item index="3-1">
                  <i class="el-icon-menu"></i>
                  商品分类
                </el-menu-item>
              </el-submenu>
              <!--订单管理-->
              <el-submenu index="4">
                <template slot="title">
                  <i class="el-icon-location"></i>
                  <span>订单管理</span>
                </template>
                <el-menu-item index="4-1">
                  <i class="el-icon-menu"></i>
                  订单列表
                </el-menu-item>
              </el-submenu>
              <!--数据统计-->
              <el-submenu index="5">
                <template slot="title">
                  <i class="el-icon-location"></i>
                  <span>数据统计</span>
                </template>
                <el-menu-item index="5-1">
                  <i class="el-icon-menu"></i>
                  数据报表
                </el-menu-item>
              </el-submenu>
            </el-menu>
          </el-aside>
        </el-aside>
        <el-main class="main">Main</el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
export default {
  methods: {
    handleOut () {
      localStorage.clear()
      this.$router.push({ name: 'Login' })
      this.$message.success('退出登录')
    }
  }
}
</script>

<style>
.container {
  height: 100%;
}

.header {
  background-color: #b3c0d1;
}

.aside {
  background-color: #d3dce6;
}

.main {
  background-color: #e9eef3;
  height: 100%;
}
.header .middle {
  line-height: 60px;
  color: #fff;
  text-align: center;
}
.header .loginout {
  line-height: 60px;
  text-decoration: none;
}
</style>

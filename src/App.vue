<template>
  <div class="common-layout">
    <el-container>
      <el-aside class="aside">
        <el-menu class="menu" background-color="#001529" text-color="#eee" router>
          <el-menu-item index="/about">
            <template #title>
              <el-icon>
                <house />
              </el-icon>首页
            </template>
          </el-menu-item>
          <el-menu-item>
            <template #title>
              <el-icon>
                <InfoFilled />
              </el-icon>基本信息
            </template>
          </el-menu-item>

          <el-sub-menu>
            <template #title>
              <el-icon>
                <message />
              </el-icon>用户管理
            </template>

            <el-menu-item index="/user">用户信息</el-menu-item>
            <el-menu-item>查询信息</el-menu-item>
          </el-sub-menu>
        </el-menu>
      </el-aside>
      <el-container>
        <el-header class="header">
          <el-icon class="fullscreen" @click="fullscreen">
            <FullScreen />
          </el-icon>

          <el-breadcrumb separator="/">
            <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
            <el-breadcrumb-item>
              <a href="/">用户管理</a>
            </el-breadcrumb-item>

          </el-breadcrumb>
          <div class="avatarDiv">
            <span>Admin</span>
            <el-dropdown>
              <img src="./assets/logo.png" alt="" class="avatar">
              <template #dropdown>
                <el-dropdown-menu>
                  <el-dropdown-item>个人信息</el-dropdown-item>
                  <el-dropdown-item>修改密码</el-dropdown-item>
                  <el-dropdown-item>退出登录</el-dropdown-item>

                </el-dropdown-menu>
              </template>
            </el-dropdown>

          </div>
        </el-header>
        <el-main>
          <router-view />
          <div class="mainInfo">
            <div class="mainCardGroup">
              <el-card class="mainCard" shadow="hover">
                <template #header>
                  <div class="card-header">
                    <span>天气</span>
                  </div>
                </template>
              </el-card>
              <el-card class="mainCard" shadow="hover">jjjj</el-card>
            </div>
            <div class="mainTable">
              <el-table :data="tableData">
                <el-table-column prop="date" label="日期" width="180" />
                <el-table-column prop="name" label="姓名" width="180" />
                <el-table-column prop="address" label="地址" />
              </el-table>
            </div>
          </div>

        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<style lang="scss" scoped>
.aside {
  width: 200px;

  .menu {
    min-height: 100vh;
  }
}

.el-menu-item {
  &:hover {
    color: #aaa;
  }
}

.change {
  height: 50%;
  font-size: 20px;
}

.header {
  background-color: #f8f8f8;
  display: flex;
  align-items: center;
  border-radius: 5px;

  .fullscreen {
    margin-right: 10px;
  }

  .avatarDiv {
    flex: 1;
    display: flex;
    justify-content: flex-end;
    align-items: center;

    .avatar {
      width: 40px;
      height: 40px;

    }

    span {
      margin-right: 10px;
    }
  }
}

.mainInfo {

  .mainCardGroup {

    display: flex;
  }

  .mainCard {
    width: 50%;
    margin: 20px 30px;
    height: 300px;

  }

  .mainTable {
    display: block;
  }
}
</style>

<script>
export default {
  data() {
    return {
      tableData: [{
        date: '2016-05-03',
        name: 'Tom',
        address: 'No. 189, Grove St, Los Angeles',
      },
      {
        date: '2016-05-02',
        name: 'Tom',
        address: 'No. 189, Grove St, Los Angeles',
      },
      {
        date: '2016-05-04',
        name: 'Tom',
        address: 'No. 189, Grove St, Los Angeles',
      },
      {
        date: '2016-05-01',
        name: 'Tom',
        address: 'No. 189, Grove St, Los Angeles',
      }]
    }
  },

  methods: {
    fullscreen() {
      document.documentElement.requestFullscreen()
    }
  },
  mounted() {
    // axios.get()
  }
}
</script>
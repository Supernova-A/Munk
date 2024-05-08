<template>
    <div class='main'>
        <div class="loginPanel">
            <div class="loginPicture">
                <img src="../assets/logo.png" alt="" width="100%">
            </div>
            <div class="loginTable">
                <el-form :model="form" label-width="auto" style="max-width: 600px">
                    <div class="loginLabel">欢迎登录管理系统</div>
                    <el-form-item label="用户名">
                        <el-input v-model="form.name" placeholder="请输入账号">
                            <template #prefix>
                                <el-icon class="el-input__icon">
                                    <user />

                                </el-icon>
                            </template>
                        </el-input>
                    </el-form-item>
                    <el-form-item label="密码">
                        <el-input show-password v-model="form.password" placeholder="请输入密码">
                            <template #prefix>
                                <el-icon class="el-input__icon">
                                    <lock />
                                </el-icon>
                            </template></el-input>
                    </el-form-item>
                    <el-form-item>
                        <el-button type="primary" @click="onSubmit" style="width:100%">登录</el-button>
                    </el-form-item>
                </el-form>
                <div class="otherOptions">
                    <div>没有注册？请 <router-link to="/register"
                            style="text-decoration: none;color: deepskyblue;">注册</router-link></div>
                    <div style="color: deepskyblue;cursor: pointer;">忘记密码</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    //import引入的组件需要注入到对象中才能使用
    components: {},
    data() {
        //这里存放数据
        return {
            form: {
                name: '',
                password: ''
            }
        }
    },
    //监听属性 类似于data概念
    computed: {},
    //监控data中的数据变化
    watch: {},
    //方法集合
    methods: {
        onSubmit(data) {
            console.log(data)
            console.log(this.form)
        }
    },
    //生命周期 - 创建完成（可以访问当前this实例）
    mounted() { },

    beforeMount() { }, //生命周期 - 挂载之前
    beforeUpdate() { }, //生命周期 - 更新之前
    updated() { }, //生命周期 - 更新之后
    activated() { }, //如果页面有keep-alive缓存功能，这个函数会触发
}
</script>
<style lang='scss' scoped>
.main {
    width: 100%;
    height: 100vh;

    display: flex;
    justify-content: center;
    align-items: center;
    background-color: deepskyblue;

    .loginPanel {
        width: 50%;
        height: 50vh;
        border: 1px solid blue;
        border-radius: 20px;
        display: flex;
        background-color: white;

        .loginPicture {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: center;
            margin: 50px;
        }

        .loginTable {
            flex: 1;
            text-align: center;
            margin: 20px;

            .loginLabel {
                color: rgb(77, 77, 77);
                font-size: 20px;
                margin: 40px 0;
                font-weight: bold;
            }

            .otherOptions {
                display: flex;
                justify-content: space-between;
                font-size: 13px;
            }
        }
    }
}
</style>
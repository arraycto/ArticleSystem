<template>
    <div class="login-wrapper">
		<div class="login-head">
			<router-link :to="{ name: 'login'}" class="login actived">登录</router-link>
			<b>.</b>
			<router-link :to="{ name: 'register'}" class="register">注册</router-link>
		</div>
		<form class="login-form" method="post">
			<div class="user-name">
				<input type="text" name="userName" placeholder="用户名">
			</div>
			<div class="password">
				<input type="password" name="password" placeholder="密码">
			</div>
				<input type="button" value="登录" class="submit" @click="dbclick">
		</form>
	</div>
</template>

<script>
export default {
    created() {
        document.title = "登录";
    },
    methods: {
        dbclick() {
            this.$toast({
                content:"show me",
                duration: 1000
            });
        }
    }
}
</script>

<style lang="less">
    body {
	background-color:#f1f1f1;
    }
    .login-wrapper {
        width: 400px;
        margin: 60px auto 0;
        text-align: center;
        padding: 50px;
        background: #fff;
        box-sizing: border-box;
        position:relative;
        .login-head {
            .login,.register {
                padding: 10px;
                color: #969696;
                display:inline-block;
                font-size: 18px;
                cursor:pointer;
                box-sizing: border-box; 
            }
            b {
                padding: 10px;
            }
            .register:hover,.login:hover {
                border-bottom: 2px solid #ea6f5a;
                cursor: pointer;
            }
            .actived {
                border-bottom: 2px solid #ea6f5a;
                font-weight: 700;
                color: #ea6f5a!important;
            }
        }
    }
    .login-form {
        margin-top:50px;
    }
    .login-form input[type="text"],input[type="password"]{
        display:block;
        width:300px;
        padding: 4px 12px 4px 35px;
        box-sizing: border-box;
        height: 50px;
        background: hsla(0,0%,71%,.1);
        line-height:50px;
        border:none;
    }
    .login-form .user-name {
        border-radius: 4px 4px 0 0;
        border: 1px solid #c8c8c8;
        border-bottom:none;
        position: relative;
    }
    .login-form .password {
        border-radius: 0 0 4px 4px;
        position: relative;
        border: 1px solid #c8c8c8;
    }
    .login-form .user-name::after {
        content:"";
        position:absolute;
        top:13px;
        left:10px;
        z-index:2;
        width:18px;
        height:18px;
        background: url("../../static/img/userName.png");
        background-size:contain;
    }
    .login-form .password::after {
        content:"";
        position:absolute;
        top:13px;
        left:10px;
        z-index:2;
        width:18px;
        height:18px;
        background: url("../../static/img/password.png");
        background-size:contain;
    }
    .login-form .submit {
        width:100%;
        height:50px;
        margin-top:30px;
        background:rgb(49,148,208);
        color:#fff;
        border-radius:25px;
        border:none;
        cursor:pointer;
        font-size:18px;
    }
    .submit:hover {
        background:#187cb7;
    }
    .login-form .register-btn {
        background: #42c02e;
    }
    .login-form .register-btn:hover {
        background: #3db922;
    }
</style>
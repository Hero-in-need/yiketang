<template>
	<view class="content">
		<u-image width="50%" height="200px" src='/static/logo.jpg'></u-image>
		<view class="input">
			<u-input v-model="userName" type="text" border placeholder="username" cursor-spacing='250' />
			<u-input v-model="password"  type="text" border placeholder="password" cursor-spacing='200' />
		</view>
		<view class="login">
			<u-button type="error" shape="circle" @tap="login" style="margin-bottom:10px">登录</u-button>
			<u-button type="error" shape="circle" @tap="register">注册</u-button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				userName:null,
				password:null
			}
		},
		onLoad() {

		},
		methods: {
		   login(){
			   uni.navigateTo({
				   url: '../student/sign',
				   // success: res => {},
				   // fail: () => {},
				   // complete: () => {}
			   });
		   },
           register(){
			   uni.navigateTo({
				   url: '../register/register',
				   // success: res => {},
				   // fail: () => {},
				   // complete: () => {}
			   });
		   }
		}
	}
</script>

<style scoped>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		background-size: 100% 100%;
		height: 100%;
	}
	.input{
		margin-top:20%;
		width:60%;
	}
	.u-input{
		margin-top:10px;
	}
	.login{
		margin-top:20px;
		width: 60%;
	}
/* 	.uni-input-input{
	    color: red;
	} */
</style>

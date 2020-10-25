<template>
	<view class="content">
		<u-image width="50%" height="200px" src='/static/logo.jpg'></u-image>
	<u-form :model="form" ref="uForm" style="margin-top:10%;background-color: rgb(255,248,220,0.3);padding:0px 10px 10px 10px">
		<u-form-item label="学号:"><u-input v-model="form.number" placeholder="请输入学号" cursor-spacing='300' /></u-form-item>
		<u-form-item label="班级:"><u-input v-model="form.class" placeholder="请输入班级" cursor-spacing='250'/></u-form-item>
		<u-form-item label="姓名:"><u-input v-model="form.name" placeholder="请输入姓名" cursor-spacing='200'/></u-form-item>
		<u-form-item label="账号:"><u-input v-model="form.userName" placeholder="请输入账号" cursor-spacing='150'/></u-form-item>
		<u-form-item label="密码:"><u-input v-model="form.password" placeholder="请输入密码"  cursor-spacing='100' /></u-form-item>
	<view style="margin-top:10px;">
	<u-button type="error" shape="circle" @tap="register">注册</u-button>
	</view>
	</u-form>
	</view>
</template>

<script>
export default {
	data() {
		return {
			form: {
				number:'',
				class:'',
				name: '',
				userName: '',
				password: ''
			},
		};
	},
	methods: {
	   register(){
		   uni.navigateTo({
			   url: '../index/index',
			   // success: res => {},
			   // fail: () => {},
			   // complete: () => {}
		   });
	   }
	}
};
</script>
<style scoped>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.u-form{
		width:73%
	}
	 .u-form-item{
		 color:white
	}
</style>
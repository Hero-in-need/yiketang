<template>
	<view class="content">
			<button :class="[state==0?'signIn1':'signIn2']" @tap="sign">{{text}}</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				userName:null,
				password:null,
				state:0,
				text:'签到'
			}
		},
		onLoad() {

		},
		methods: {
      //      register(){
			   // uni.navigateTo({
				  //  url: '../register/register',
				  //  // success: res => {},
				  //  // fail: () => {},
				  //  // complete: () => {}
			   // });
		   // }
		   sign(){
		   	this.state=1;
			this.text='签到成功';
			   uni.navigateTo({
				   // url: '../student/index',
				   url: '../master/index',
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
		align-items: center;
		justify-content: center;
		margin-top: 80%;
	}
	.signIn1{
		margin:10px;width: 150px;height: 150px;border:1px sold transparent ;border-radius:50%;font-size:60px;background-color: #007AFF;color:white;line-height:150px
	}
	.signIn2{
		margin:10px;width: 150px;height: 150px;border:1px sold transparent ;border-radius:50%;font-size:53px;background-color: #18B566;color:white;line-height:75px
	}
</style>

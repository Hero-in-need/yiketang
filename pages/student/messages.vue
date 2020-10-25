<template>
	<view class="content">
		<view v-for="(student,index) in students">
				<view class="iconfont icon-yewutubiao_xueshengchaxun" style="font-size:100px;color:#ff9900;float:left;padding-left:10%"></view>
				<view style="float: left">
					<h1>ID:<span style="color:#dd6161">{{index}}</span></h1>
					<h2>学号:<span style="color:#f29100">{{student.number}}</span></h2>
					<h2>姓名:<span style="color:#f29100">{{student.name}}</span></h2>
					<h2>班级:<span style="color:#f29100">{{student.class}}</span></h2>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props:["state"],
		data() {
			return {
				students:[{
					number:5120184430,
					class:'物联1802',
					name:'曾维鹏'
				},{
					number:5120184530,
					class:'电子1801',
					name:'徐锐'
				},{
					number:5120184430,
					class:'自动1804',
					name:'袁家钱'
				},{
					number:5120184430,
					class:'自动1804',
					name:'袁家钱'
				},{
					number:5120184430,
					class:'自动1804',
					name:'袁家钱'
				},{
					number:5120184430,
					class:'自动1804',
					name:'袁家钱'
				},{
					number:5120184430,
					class:'自动1804',
					name:'袁家钱'
				}]
			       }
              },
			  watch: {
					state(val){
						if(val==0){
						this.students=[{
							number:5120184430,
							class:'物联1802',
							name:'曾维鹏'
						},{
							number:5120184530,
							class:'电子1801',
							name:'徐锐'
						},{
							number:5120184430,
							class:'自动1804',
							name:'袁家钱'
						},{
							number:5120184430,
							class:'自动1804',
							name:'袁家钱'
						},{
							number:5120184430,
							class:'自动1804',
							name:'袁家钱'
						},{
							number:5120184430,
							class:'自动1804',
							name:'袁家钱'
						},{
							number:5120184430,
							class:'自动1804',
							name:'袁家钱'
						}]}
						 if(val==1){
						this.students=[{
					number:5120184430,
					class:'物联1802',
					name:'机器人'
				},{
					number:5120184530,
					class:'电子1801',
					name:'徐锐'
				},{
					number:5120184430,
					class:'自动1804',
					name:'袁家钱'
				}]}
				else if(val==2){
						this.students=[{
					number:5120184430,
					class:'物联1802',
					name:'迟到了啊'
				},{
					number:5120184530,
					class:'电子1801',
					name:'徐锐'
				},{
					number:5120184430,
					class:'自动1804',
					name:'袁家钱'
				},{
					number:5120184430,
					class:'自动1804',
					name:'袁家钱'
				}]}
					}	
		      }
	}
</script>

<style scoped>
	.content {
		display: flex;
		flex-direction: column;
		background-color: #82848a;
	}
</style>

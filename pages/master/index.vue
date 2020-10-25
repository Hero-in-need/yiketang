<template>
	<view >
	  <u-subsection :list="list" :current="current"  mode="subsection" @change="sectionChange" active-color="#2979ff" style="margin-top:10rpx" ></u-subsection>
	              <view v-if="current === 0">
					  <allMessages :state="0"/>
	              </view>
	              <view v-if="current === 1">
                      <allMessages :state="1"/>
	              </view>
	              <view v-if="current === 2">
                      <allMessages :state="2"/>
	              </view>
	  </view>
</template>

<script>
	import allMessages from './allMessages.vue';
	export default {
		components: {
		    allMessages
		},
		data() {
			return {
					list: [
						{
							name: '已签到'
						}, 
						{
							name: '未签到'
						}, 
						{
							name: '迟到'
						},
					],
				current: 0
			}
		},
		methods:{
			sectionChange(index) {
				this.current = index;
			}
		}
	}
</script>
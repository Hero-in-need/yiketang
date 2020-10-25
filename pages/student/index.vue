<template>
	<view >
	  <u-subsection :list="list" :current="current"  mode="subsection" @change="sectionChange" active-color="#2979ff" style="margin-top:10rpx" ></u-subsection>
	              <view v-if="current === 0">
					  <messages :state="0"/>
	              </view>
	              <view v-if="current === 1">
                      <messages :state="1"/>
	              </view>
	              <view v-if="current === 2">
                      <messages :state="2"/>
	              </view>
	  </view>
</template>

<script>
	import messages from './messages.vue';
	export default {
		components: {
		    messages
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
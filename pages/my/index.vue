<template>
	<view class="my">
		
		<view class="my-header">
			<view>
				<image src="../../static/image/bg/find_bg.jpg" style="width: 40px; height: 40px;"></image>
			</view>
			<view style="margin-left: 10px;">
				<text style="font-size: 14px; font-weight: bold;">美食小编</text><br />
				<text style="font-size: 12px; color: #c2c2c2;">13888888888</text>
			</view>
		</view>
		<uni-list style="margin-top: 10px;">
			<uni-list-item title="我的资料"></uni-list-item>
			<uni-list-item title="我的发布"></uni-list-item>
			<uni-list-item title="我的收藏"></uni-list-item>
			<uni-list-item title="设置"></uni-list-item>
		</uni-list>
		<view style="margin-top: 30px; padding: 0 20px;">
			<button style="height: 30px; line-height: 30px; background-color: #f76969; color: #FFFFFF; font-size: 14px;">退出登录</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style scoped lang="scss">
.my{
	background: #f8f8f8;
}
.my-top{
		height: 30px;
		line-height: 30px;
		text-align: center;
		background-color: #cecece;
	}
	.my-header{
		padding: 15px 10px;
		background-color: #FFFFFF;
		display: flex;
		margin-top: 30px;
	}
</style>

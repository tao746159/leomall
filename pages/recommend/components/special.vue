<template>
	<view class="special">
		<view class="special-left">
			 <view class="special-left-text">
					<text style="color: #ffffff">今日特惠</text>
				</view>
				<view class="special-left-summ">
					<text style="font-weight: bold;">休闲食品</text> <br />
					<text>红枣核桃</text>
				</view>
				
		</view>
		<view class="special-right">
			<view class="special-r-top">
				<text style="font-weight: 'bold'">8.8折起</text> <br />
				<text>好吃漂亮糖果</text>
			</view>
			<view class="special-r-bot">
				<text style="font-weight: 'bold'">全场半价</text> <br />
				<text>薯片薯条饼干</text>
			</view>
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

<style lang="scss">
.special{
	display: flex;
	height: 120px;
	margin-top: 10px;
	.special-left {
		background-image: url('/static/image/bg/special/food_bg.jpg');
		background-size: 100% 100%;
		flex: 1;
		height: 100%;
		margin-right: 2px;
		.special-left-text{
			width: 80px;
			height: 30px;
			background-color:#ed7a32;
			line-height: 30px;
			text-align: center;
		}
		.special-left-summ{
			margin-left: 10px;
			margin-top: 10px;
			color: #004f00;
			font-size: 14px;
		}
	}
	.special-right{
		flex: 1;
		margin-left: 2px;
		.special-r-top, .special-r-bot{
			height: 48px;
			background-size: 100% 100%;
			font-size: 14px;
			color: #004f00;
			padding: 10px 0 0 10px;
		}
		.special-r-top{
			background-image: url('/static/image/bg/special/tang_bg.jpg');
		}
		.special-r-bot{
			margin-top: 4px;
			background-image: url('/static/image/bg/special/lingshi_bg.jpg');
		}
	}
}
</style>

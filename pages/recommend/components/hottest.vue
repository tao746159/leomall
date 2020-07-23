<template>
	<view class="hottest">
		<view class="title">
			<uni-icons type="shop" size="20" style="vertical-align: middle;" color="#E54A38"></uni-icons>
			<text style="margin-left: 10px; font-size: 16px;vertical-align: middle;">最热商品</text>
		</view>
		<view  class="hottest-content">
			<view v-for="(item, index) in list" class="content" :key="index">
				<view>
					<image :src="item.src"></image>
					<view class="content-title">
						<text>{{item.title}}</text>
					</view>
					<view class="content-pirce">
						<text style="font-size: 14px;">{{item.pice}}</text>
						<text style="font-size: 12px; color: #333333;">{{item.paying}}</text>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props:['list'],
		data() {
			return {
			}
		},
		created() {
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
	.hottest{
		margin-top: 10px;
		.title{
			text-align: center;
			height: 30px;
			line-height: 30px;
		}
		.hottest-content{
			display: flex;
			flex-direction: row;
			flex-wrap: wrap;
			justify-content:space-between;
			padding: 10px;
			.content {
				margin: 5px 0;
				padding-top: 10px;
				width: calc(50% - 5px);
				box-sizing: border-box;
				height: 220px;
				text-align: center;
				box-shadow: 1px 1px 4px #888888;
				image {
					width: 130px;
					height: 130px;
				}
				.content-title{
					font-size: 12px;
					overflow: hidden;
					text-overflow:ellipsis;
					white-space: nowrap;
					padding: 0 5px;
				}
				.content-pirce{
					margin-top: 5px;
					padding: 0 5px;
					display: flex;
					text-align: left;
					color: #E54A38;
					line-height: 20px;
					justify-content: space-between;
				}
			}
		}
	}
</style>

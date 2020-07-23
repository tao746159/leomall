<template>
	<view class="find-list-wapper">
		<view v-for="(item, index) in list" class="find-list" :key="index">
			<view class="find-list-title">
				<text>{{item.title}}</text>
			</view>
			<view class="find-list-content">
				<view class="find-list-left">
					<image :src="item.src"></image>
				</view>
				<view class="find-list-right">
					<text class="find-list-summay">{{item.summay}}</text>
					<view class="find-tags">			
							<text class="tag">{{item.tag}}</text>
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
		methods: {

		},
		created() {

			
		}
	}
</script>

<style lang="scss">
	.find-list-wapper {
		margin-top: 140px;
		height: 100%;
		.find-list{
			margin-top: 10px;
			background-color: #FFFFFF;
			height: 150px;
			padding: 10px;
			border-bottom: 1px solid #b3b3b3;
			.find-list-title{
				font-size: 14px;
				font-weight: bold;
			}
			.find-list-content{
				display: flex;
				flex-direction: row;
				margin-top: 10px;
				view{
					image{
						width: 120px;
						height: 120px;
					}
				}
				.find-list-left{
					text-align: center;
					margin-right: 20px;
				}
				.find-list-right{
					font-size: 14px;
					padding-top: 5px;
					.find-tags{
						display: flex;
						margin-top: 20px;
						
						.tag{
							background-color: #e2e2e2;
							color: #555555;
							padding: 2px 3px;
							margin-right: 10px;
						}
					}
					.find-list-summay{
						margin: 8px 0; 
						display: block;
						text-overflow: -o-ellipsis-lastline;
						overflow: hidden;
						text-overflow: ellipsis;
						display: -webkit-box;
						-webkit-line-clamp: 3;
						-webkit-box-orient: vertical;

					}
				}
			}
		}
		
	}
</style>

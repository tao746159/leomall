<template>
	<view class="food-chat-list">
	<view class="chat-list-wapper" v-for="(item,index) in list" :key="index">
		<view class="chat-list-wapper-top">
			<image :src="item.autherImg" style="width: 25px; height: 25px; border-radius: 50%; vertical-align: middle;"></image>
			<text style="margin-left: 5px; font-size: 14px;">{{item.auther}}</text>
		</view>
		<view class="food-chat-summay">
			<text>
				{{item.summay}}
			</text>
		</view>
		
		<view class="food-chat-image"></view>
		<view class="food-chat-footer">
			<view>
				<text style="color: #9d9d9d;">2020-05-26 发布</text>
			</view>
			<view>
				<view style="color: #9d9d9d;">
					<uni-icons type="hand-thumbsup" @click="handleNumadd(index)" color="#9d9d9d" ></uni-icons>
					<span>{{num[index]}}</span>
				</view>
			</view>
		</view>
	</view>
	</view>
</template>

<script>
	export default {
		props: ['list','num'],
		data() {
			return {
			}
		},
		methods: {
			handleNumadd(index) {
				this.$emit('handleSetNum', index)
			}
		}
	}
</script>

<style scoped lang="scss">
	.food-chat-list{
		padding: 10px;
		.chat-list-wapper{
			margin-top: 30px;
			margin-bottom: 20px;
		}
		.food-chat-summay{
			margin-top: 10px;
			font-size: 12px;
		}
		.food-chat-footer{
			margin-top: 10px;
			font-size: 12px;
			display: flex;
			justify-content: space-between;
		}
	}
</style>

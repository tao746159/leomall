<template>
	<view>
		<view class="top">
			<view class="top-left">
				<uni-icons type="plus" size="20"></uni-icons>
				
			</view>
			<view class="top-search">
				<input class="input" />
			</view>
			<view class="top-right">
				<uni-icons type="email" size="20"></uni-icons>
			</view>
		</view>
		<Caroular></Caroular>
		<Special></Special>
		<Hottest :list="list"></Hottest>
	</view>
</template>

<script>
	import axios from 'axios'
	import Caroular from './components/caroular'
	import Special from './components/special'
	import Hottest from './components/hottest'
	export default {
		components:{Caroular,Special,Hottest},
		data() {
			return {
				list: []
			}
		},
		created() {
			uni.request({
				url: 'http://www.leother.cool:3002/api/homelist',
				success: (res) => {
					console.log(res)
					if(res.data.code === 200) {
						this.list = res.data.list
					}
				}
			})
			
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
	.top{
		height: 40px;
		background-color: #f6f5fa;
		display: flex;
		flex-direction: row;
		align-items: center;
		width: 100%;
		flex: 1;
		position: fixed;
		top: 0;
		left: 0;
		z-index: 2;
		.top-left{
			width: 15%;
			justify-content: center;
			text-align: center;
		}
		.top-search {
			max-width: 80%;
			flex: 6
		}
		.input {
			background-color: #e2e2e2; 
			border-radius: 3px;
			height: 26px;
			font-size: 14px;
			text-indent: 10px;
		}
		.top-right {
			flex: 1;
			text-align: center;
			.top-image{
				max-width: 20px;
				max-height: 20px;
			}
		}
	}
	
</style>

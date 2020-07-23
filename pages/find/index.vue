<template>
	<view class="find">
		<view class="find-top">
			
			<view class="find-top-tabs">
				<view v-for="(item, index) in tabs"  :class="[item.name, 'tabs']" :key="index">
					<view class="top-tabs-item" @click="handleTab(item.name)">
						<view style="padding-top: 5px;">
							<text style="display: block;">{{item.text}}</text>
						</view>
						<view style="padding-top: 3px;"><text style="display: block;">{{item.summay}}</text></view>
						<view style="padding-top: 5px;"><image :src="item.type" style="width: 30px; height: 30px;" /></view>
					</view>
				</view>
			</view>
		</view>
		<find-list :list="list"></find-list>
	</view>
</template>

<script>
	import FindList from './components/findlist.vue'
	export default {
		components:{FindList},
		data() {
			return {
				tabs: [
					{
						type: '../../static/image/icons/food.png',
						text: '食材',
						summay: '诞生之源',
						name: 'people',
						backg: '#6bb031'
					},
					{
						type: '../../static/image/icons/caipu.png',
						text: '菜谱',
						summay: '精选菜谱',
						name: 'caipu',
						backg: '#f39730'
					},
					{
						type: '../../static/image/icons/zhuanti.png',
						text: '专题',
						summay: '品味美食',
						name: 'zhuant',
						backg: '#8a7db3'
					},
					{
						type: '../../static/image/icons/jiankang.png',
						text: '健康',
						summay: '健康攻略',
						name: 'jiank',
						backg: '#df6572'
					}
				],
				active: 'people',
				list: []
			}
		},
		methods: {
			handleTab(name) {
				this.active = name
		}
	},
	created() {
		uni.request({
			method:'GET',
			url: 'http://leother.cool:3002/api/findlist',
			success:(res)=> {
				if(res.data.code === 200) {
			
					this.list = res.data.list
				}
			}
		})
	}
	}
</script>

<style lang="scss">
	.find{
		background-color: #f3f4f6;
		height: 100%;
		.find-top{
			height: 120px;
			padding: 0 10px;
			position: fixed;
			top: 0;
			left: 0;
			width: 100%;
			z-index: 2;
			background-color: #FFFFFF;
			box-sizing: border-box;
			.find-top-icon{
				padding-top: 20px;
				text-align: center;
			}
			.find-top-tabs{
				width: 100%;
				height: 120px;
				background-color: #FFFFFF;
				border-radius: 20px 20px 0 0;
				display: flex;
				flex-direction: row;
				border-bottom: 1px solid #939393;
			}
			.tabs{
				flex: 0 0 25%;
				text-align: center;
				margin-top: 10px;
				height: 100px;
				.top-tabs-item {
					margin-left: 3px;
					margin-right: 3px;
					height: 100px;
					border-radius: 3px;
					justify-content: center;
					view{
						padding: 8px 0;
					}
					image{
						width: 20px;
						height: 20px;
						display: block;
						margin: 0 auto;
						margin-bottom: 2px;
					}
					text{
						font-size: 12px;
						color: #FFFFFF;
					}
				}
				.top-tabs-item.active{
					text{
						color: #ad663c;
					}
				}
			}
			.tabs.people .top-tabs-item{
				background-color: #6bb031;
			}
			.tabs.caipu .top-tabs-item{
				background-color: #f39730;
			}
			.tabs.zhuant .top-tabs-item{
				background-color: #8a7db3;
			}
			.tabs.jiank .top-tabs-item{
				background-color: #df6572;
			}
		}
	}
</style>

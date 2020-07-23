<template>
	<view class="food-chat">
		<view class="food-header">
			<view class="food-chat-top">
				<text>食话</text>
			</view>
			<view class="tabs">
				<view :class="[tabs === 'new' ? 'active' : '','tabs-left']" @click="handleSort('new')">
					<text>最新话题</text>
				</view>
				<view :class="[tabs === 'hot' ? 'active' : '','tabs-right']"  @click="handleSort('hot')">
					<text>最热话题</text>
				</view>
			</view>
		</view>
		<view class="food-chat-content">		
			<FoodChatList :list="list" :num="num" @handleSetNum="handleSetNum"></FoodChatList>
		</view>
	</view>
</template>

<script>
	import FoodChatList from './components/foodchatlist.vue'
	export default {
		components:{FoodChatList},
		data() {
			return {
				tabs: 'new',
				num: [],
				list: [
					{
						autherImg: 'https://i2.tiimg.com/722699/9fc324e430dae05a.jpg',
						auther: '美食小编',
						summay: '三杯鸡最先起源于江西，2008年，这道菜还入选了奥运主菜单.后来，三杯鸡传到了台湾，最先江西是以米酒，猪油，酱油各一杯来烹调，以此起名为三杯鸡，到了台湾后，台湾人对它进行了小改造，将油腻的猪油换成了清淡的食用油，而且加入了一种独特的香料——九层塔',
						date: '2020-05-26 发布'
					},
					{
						autherImg: 'https://i2.tiimg.com/722699/9a023adbefe8d565.jpg',
						auther: '美食小编2',
						summay: '三杯鸡最先起源于江西，2008年，这道菜还入选了奥运主菜单.后来，三杯鸡传到了台湾，最先江西是以米酒，猪油，酱油各一杯来烹调，以此起名为三杯鸡，到了台湾后，台湾人对它进行了小改造，将油腻的猪油换成了清淡的食用油，而且加入了一种独特的香料——九层塔',
						date: '2020-05-25 发布'
					},
					{
						autherImg: 'https://i2.tiimg.com/722699/dcca36f497b10195.jpg',
						auther: '美食小编',
						summay: '三杯鸡最先起源于江西，2008年，这道菜还入选了奥运主菜单.后来，三杯鸡传到了台湾，最先江西是以米酒，猪油，酱油各一杯来烹调，以此起名为三杯鸡，到了台湾后，台湾人对它进行了小改造，将油腻的猪油换成了清淡的食用油，而且加入了一种独特的香料——九层塔',
						date: '2020-05-26 发布'
					},
					{
						autherImg: 'https://i1.fuimg.com/722699/c76ca046558e7ab4.jpg',
						auther: '美食小编2',
						summay: '三杯鸡最先起源于江西，2008年，这道菜还入选了奥运主菜单.后来，三杯鸡传到了台湾，最先江西是以米酒，猪油，酱油各一杯来烹调，以此起名为三杯鸡，到了台湾后，台湾人对它进行了小改造，将油腻的猪油换成了清淡的食用油，而且加入了一种独特的香料——九层塔',
						date: '2020-05-25 发布'
					},
					{
						autherImg: 'https://i1.fuimg.com/722699/5eb03894f99bd988.jpg',
						auther: '美食小编',
						summay: '三杯鸡最先起源于江西，2008年，这道菜还入选了奥运主菜单.后来，三杯鸡传到了台湾，最先江西是以米酒，猪油，酱油各一杯来烹调，以此起名为三杯鸡，到了台湾后，台湾人对它进行了小改造，将油腻的猪油换成了清淡的食用油，而且加入了一种独特的香料——九层塔',
						date: '2020-05-26 发布'
					},
					{
						autherImg: 'https://i1.fuimg.com/722699/69041e7b10049c02.jpg',
						auther: '美食小编2',
						summay: '三杯鸡最先起源于江西，2008年，这道菜还入选了奥运主菜单.后来，三杯鸡传到了台湾，最先江西是以米酒，猪油，酱油各一杯来烹调，以此起名为三杯鸡，到了台湾后，台湾人对它进行了小改造，将油腻的猪油换成了清淡的食用油，而且加入了一种独特的香料——九层塔',
						date: '2020-05-25 发布'
					}
				]
			}
		},
		methods: {
			handleNumadd() {
				this.num ++
			},
			handleSetNum(index) {
				this.$set(this.num, index, this.num[index]+1)
			},
			handleSort(item) {
				this.tabs = item
			}
		},
		created() {
			for(let i = 0; i< this.list.length; i++) {
				this.num[i] = 0
			}
		
		}
	}
</script>

<style lang="scss">
	.food-header{
		position: fixed;
		width: 100%;
		top: 0;
		left: 0;
		padding-bottom: 20px;
		background-color: #FFFFFF;
		z-index: 3;
	}
	.food-chat-top{
		height: 30px;
		line-height: 30px;
		text-align: center;
		background-color: #cecece;
	}
	.tabs{
		display: flex;
		justify-content: center;
		margin-top: 20px;
		view{
			padding: 5px 10px;
			border: 1px solid #dd4f4e;
		}
		view.active{
			background-color: #dd4f4e;
			color: #FFFFFF;
		}
		.tabs-left{
			border-radius: 3px 0 0 3px;
		}
		.tabs-right{
			border-radius: 0 3px 3px 0;
		}
	}
	.food-chat-content{
		margin-top: 83px;
	}

</style>

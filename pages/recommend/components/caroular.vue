<template>
	<view style="margin-top: 40px;">
		<uni-swiper-dot :info="info" :current="current" field="content" :mode="mode">
			<swiper class="swiper-box" @change="change">
				<swiper-item v-for="(item ,index) in info" :key="index">
					<view class="swiper-item">
						<image :src="item.src"></image>
					</view>
				</swiper-item>
			</swiper>
		</uni-swiper-dot>
	</view>
</template>

<script>

	export default {

		data() {
			return {
				info: [{
					src: '/static/image/swipe/hb_01.jpg'
				}, {
					src: '/static/image/swipe/hb_02.jpg'
				}, {
					src: '/static/image/swipe/hb_03.jpg'
				}],
				current: 0,
				mode: 'round',
			}
		},
		methods: {
			change(e) {
				this.current = e.detail.current;
			}
		}
	}
</script>

<style lang="scss">
.swiper-item{
	image{
		width: 100%;
		max-width: 100%;
	}
}
</style>

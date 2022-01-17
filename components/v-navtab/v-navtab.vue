<template>
	<view>
		<view class="v-navtab">
			<u-tabs
				:list="list"
				:current="current"
				@change="changeTab"
				:name="name"
				:duration="duration"
				:active-color="activeColor"
				:is-scroll="isScroll"
				:inactive-color="inactiveColor"
				:bar-width="barWidth"
				:bar-height="barHeight"
				:bg-color="bgColor"
				:bold="bold"
			></u-tabs>
		</view>
		<u-gap height="80"></u-gap>
	</view>
</template>

<script>
export default {
	props: {
		list: {
			type: Array,
			default: () => []
		},
		name: {
			type: String,
			default: 'name'
		},
		isScroll: {
			type: Boolean,
			default: false
		},
		duration: {
			type: [Number, String],
			default: '0.2'
		},
		// 选中项的颜色
		activeColor: {
			type: String,
			default: '#E54A48'
		},
		// 未选中项的颜色
		inactiveColor: {
			type: String,
			default: '#303133'
		},
		// 菜单底部移动的bar的宽度，单位rpx
		barWidth: {
			type: [String, Number],
			default: 80
		},
		// 移动bar的高度
		barHeight: {
			type: [String, Number],
			default: 6
		},
		bgColor: {
			type: String,
			default: '#fff'
		},
		bold: {
			type: Boolean,
			default: true
		},
	},
	data() {
		return {
			current: 0
		}
	},
	methods: {
		changeTab(e) {
			this.current = e
			this.$emit('change', e)
		}
	}
}
</script>

<style lang="scss">
.v-navtab {
	position: fixed;
	top: 0;
	width: 750rpx;
	border-bottom: 1rpx solid #eee;
	z-index: 999;
}
</style>

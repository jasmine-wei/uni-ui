<template>
	<view class="content">
		<!-- :start-date="'2019-2-10'"
		:end-date="'2019-3-15'" -->
		<text class="title">禁止滚动</text>
		<view class="calendar-box">
			<uni-calendar slide="none" />
		</view>
		<text class="title">不固定高度</text>
		<view class="calendar-box">
			<uni-calendar :fixedHeihgt="false" slide="none" />
		</view>
		<text class="title">日历水平滚动切换</text>
		<view class="calendar-box">
			<uni-calendar slide="horizontal" />
		</view>
		<text class="title">日历垂直滚动切换</text>
		<view class="calendar-box">
			<uni-calendar slide="vertical" />
		</view>
		<text class="title">禁止选择今天之前的日期</text>
		<view class="calendar-box">
			<uni-calendar :disable-before="true" slide="none" />
		</view>
		<text class="title">选择范围 （2019-02-10 ～ 2019-05-10）</text>
		<view class="calendar-box">
			<uni-calendar start-date="2019-02-10" end-date="2019-05-10" slide="none" />
		</view>
		<text class="title">自定义当前日期 （2019-03-10）</text>
		<view class="calendar-box">
			<uni-calendar :disable-before="true" date="2019-03-10" slide="none" />
		</view>
		<text class="title">开启农历</text>
		<view class="calendar-box">
			<uni-calendar :lunar="true" slide="none" />
		</view>
		<text class="title">事件</text>
		<view class="calendar-box">
			<uni-calendar :lunar="false" :disable-before="false" slide="horizontal" @change="change" @to-click="toClick" />
		</view>
		<view>change: 当前选择时间：{{cahngInfo}}</view>
		<view>to-click: 当前选择时间：{{clickInfo}}</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				clickInfo: '',
				cahngInfo: '',
				val: '',
				maskShow: false
			};
		},
		onLoad() {},
		methods: {
			moveHandle() {},
			closeMask() {
				this.maskShow = false;
			},
			change(e) {
				this.cahngInfo = e.fulldate;
			},
			toClick(e) {
				this.clickInfo = e.fulldate;
			}
		}
	};
</script>

<style>
	page {
		background: #fff;
	}

	.content {
		padding: 20upx;
		padding-bottom: 60upx;
		font-size: 26upx;
	}

	.content>.title {
		line-height: 80upx;
		font-weight: bold;
		color: #333;
		font-size: 30upx;
		border-left: 2px #0d9ebb solid;
		padding-left: 20upx;
	}

	.content .calendar-box {
		border-radius: 15upx;
		overflow: hidden;
		border: 1px #eee solid;
		margin-bottom: 30upx;
	}

	.content .button-group {
		margin-top: 20upx;
	}

	.content .button-group button {
		margin-top: 20upx;
		font-size: 30upx;
		line-height: 90upx;
	}

	.content .clock-info {
		margin: 20upx 0;
		border: 1px #ccc solid;
		padding: 15upx;
	}
</style>

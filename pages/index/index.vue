<template>
	<view class="content">
		<view class="top-bar">
			<view class="top-bar-left">
				<image src="../../static/img/m7wr6c4l.png" mode=""></image>
			</view>
			<view class="top-bar-center">
				<image src="../../static/img/index/chaowei2.png" mode=""></image>
			</view>
			<view class="top-bar-right">
				<view class="top-bar-eye">

				</view>
				<view class="top-bar-adder">

				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss">
	.content{
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.top-bar{
		height: 88rpx;
		width: 100%;
		background:$uni-bg-color ;
		box-shadow:0px 1px 0px 0px rgba(0,0,0,0.1);
		display: flex;
		justify-content: space-around;
		.top-bar-left{
			image{
				width: 68px;
				height:68px;
				border-radius: $uni-border-radius-base;
			}

		}
		.top-bar-center{
			image{
				width: 88rpx;
				height: 68rpx;
			}
		}
		.top-bar-right{
			display: flex;
			flex-direction: row;
			justify-content: space-between;
			view{
				// border: 1px solid #2C405A;
			}
		}
	}
	
</style>

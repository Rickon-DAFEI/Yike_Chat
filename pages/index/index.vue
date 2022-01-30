<template>
	<view class="content">
		<view class="top-bar">
			<view class="top-bar-left">
				<image src="../../static/img/m7wr6c4l.png" mode=""></image>
			</view>
			<view class="top-bar-center">
				<image src="../../static/img/index/logo.png" mode=""></image>
			</view>
			<view class="top-bar-right">
				<view class="top-bar-eye">

				</view>
				<view class="top-bar-adder">
					<svg t="1643554622449" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="3367" width="200" height="200"><path d="M512 74.666667C270.933333 74.666667 74.666667 270.933333 74.666667 512S270.933333 949.333333 512 949.333333 949.333333 753.066667 949.333333 512 753.066667 74.666667 512 74.666667z m0 810.666666c-204.8 0-373.333333-168.533333-373.333333-373.333333S307.2 138.666667 512 138.666667 885.333333 307.2 885.333333 512 716.8 885.333333 512 885.333333z" p-id="3368"></path><path d="M682.666667 480h-138.666667V341.333333c0-17.066667-14.933333-32-32-32s-32 14.933333-32 32v138.666667H341.333333c-17.066667 0-32 14.933333-32 32s14.933333 32 32 32h138.666667V682.666667c0 17.066667 14.933333 32 32 32s32-14.933333 32-32v-138.666667H682.666667c17.066667 0 32-14.933333 32-32s-14.933333-32-32-32z" p-id="3369"></path></svg>
					<svg t="1643554574869" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="3232" width="200" height="200"><path d="M945.066667 898.133333l-189.866667-189.866666c55.466667-64 87.466667-149.333333 87.466667-241.066667 0-204.8-168.533333-373.333333-373.333334-373.333333S96 264.533333 96 469.333333 264.533333 842.666667 469.333333 842.666667c91.733333 0 174.933333-34.133333 241.066667-87.466667l189.866667 189.866667c6.4 6.4 14.933333 8.533333 23.466666 8.533333s17.066667-2.133333 23.466667-8.533333c8.533333-12.8 8.533333-34.133333-2.133333-46.933334zM469.333333 778.666667C298.666667 778.666667 160 640 160 469.333333S298.666667 160 469.333333 160 778.666667 298.666667 778.666667 469.333333 640 778.666667 469.333333 778.666667z" p-id="3233"></path></svg>
		
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
			align-items: center;
			justify-content: center;
			image{
				width: 88rpx;
				height: 60rpx;
			}
		}
		.top-bar-right{
			display: flex;
			flex-direction: row;
			justify-content: space-between;
			svg{
				width: 60px;
				height: 60px;
			}
		}
	}
	
</style>

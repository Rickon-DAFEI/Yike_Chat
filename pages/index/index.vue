<template>
	<view class="content">
		<view class="top-bar">
			<navigator url="../signin/signin" hover-class="none" class="top-bar-left">
				<image src="../../static/images/img/four.png" class="my-img"></image>
			</navigator>
			<view class="top-bar-center">
				<image src="../../static/images/index/logo.png" class="logo"></image>
			</view>
			<view class="top-bar-right">
				<view class="search" @tap="toSearch"><svg t="1643554622449" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="3367" width="200" height="200"><path d="M512 74.666667C270.933333 74.666667 74.666667 270.933333 74.666667 512S270.933333 949.333333 512 949.333333 949.333333 753.066667 949.333333 512 753.066667 74.666667 512 74.666667z m0 810.666666c-204.8 0-373.333333-168.533333-373.333333-373.333333S307.2 138.666667 512 138.666667 885.333333 307.2 885.333333 512 716.8 885.333333 512 885.333333z" p-id="3368"></path><path d="M682.666667 480h-138.666667V341.333333c0-17.066667-14.933333-32-32-32s-32 14.933333-32 32v138.666667H341.333333c-17.066667 0-32 14.933333-32 32s14.933333 32 32 32h138.666667V682.666667c0 17.066667 14.933333 32 32 32s32-14.933333 32-32v-138.666667H682.666667c17.066667 0 32-14.933333 32-32s-14.933333-32-32-32z" p-id="3369"></path></svg></image></view>
				<view class="add"><svg t="1643554574869" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="3232" width="200" height="200"><path d="M945.066667 898.133333l-189.866667-189.866666c55.466667-64 87.466667-149.333333 87.466667-241.066667 0-204.8-168.533333-373.333333-373.333334-373.333333S96 264.533333 96 469.333333 264.533333 842.666667 469.333333 842.666667c91.733333 0 174.933333-34.133333 241.066667-87.466667l189.866667 189.866667c6.4 6.4 14.933333 8.533333 23.466666 8.533333s17.066667-2.133333 23.466667-8.533333c8.533333-12.8 8.533333-34.133333-2.133333-46.933334zM469.333333 778.666667C298.666667 778.666667 160 640 160 469.333333S298.666667 160 469.333333 160 778.666667 298.666667 778.666667 469.333333 640 778.666667 469.333333 778.666667z" p-id="3233"></path></svg></image></view>		
			</view>
		</view>
		<view class="main">
			<view class="friends">
				<view class="friend-list" >
					<view class="friend-list-l">
						<text class="tip">1</text>
						<image src="../../static/images/index/apply.png"></image>
					</view>
					<view class="friend-list-r">
						<view class="top">
							<view class="name">好友申请</view>
							<view class="time">13:43</view>
						</view>
						<view class="news">茫茫人海，相聚便是缘分</view>
					</view>
				</view>
			</view>
			<view class="friends">
				<view class="friend-list" v-for="(item,index) in friends" :key="index">
					<view class="friend-list-l">
						<text class="tip" v-if="item.tip>0">{{item.tip}}</text>
						<image :src="item.imgurl"></image>
					</view>
					<view class="friend-list-r">
						<view class="top">
							<view class="name">{{item.name}}</view>
							<view class="time">{{changeTime(item.time)}}</view>
						</view>
						<view class="news">{{item.news}}</view>
					</view>
				</view>
			</view>
		</view>
		
	</view>
</template>

<script>
	import datas from '../../commons/js/datas.js';
	import myfun from '../../commons/js/myfun.js';
	export default {
		data() {
			return {
				friends:[],
			}
		},
		onLoad() {
			this.getFrinds();
		},
		methods: {
			changeTime: function(date){
				return myfun.dateTime(date);
			},
			getFrinds: function(){
				this.friends = datas.frineds();
				for(let i=0;i<this.friends.length;i++){
					this.friends[i].imgurl='../../static/images/img/'+this.friends[i].imgurl;
				}
				//console.log(this.friends);
			},
			//跳转到搜索页面
			toSearch: function(){
				uni.navigateTo({
				    url: '../search/search',
				});
			},
		}
	}
</script>

<style lang="scss">
	@import "../../commons/css/mycss.scss";
	.top-bar{
		background:rgba(255,255,255,0.96);
		border-bottom:1px solid $uni-border-color;
	}
	.main{
		padding-top: 104rpx;
		padding-bottom: $uni-spacing-col-base;
		//border: 1px solid red;
	}
	.friend-list{
		height: 96rpx;
		padding: 16rpx $uni-spacing-col-base;
		&:active{
			background-color: $uni-bg-color-grey;
		}
		.friend-list-l{
			position: relative;
			float: left;
			image{
				width:96rpx;
				height:96rpx;
				border-radius:$uni-border-radius-base;
				background-color: $uni-color-primary;
			}
			.tip{
				position: absolute;
				z-index: 10;
				top: -8rpx;
				left: 68rpx;
				min-width:20rpx ;
				padding: 0 8rpx;
				height:36rpx;
				background:$uni-color-warning;
				border-radius:18rpx;
				font-size: $uni-font-size-sm;
				color: $uni-text-color-inverse;
				line-height: 36rpx;
				text-align: center;
			}
		}
		.friend-list-r{
			padding-left: 128rpx;
			.top{
				height: 50rpx;
				.name{
					float: left;
					font-size:36rpx;
					font-weight:400;
					color:$uni-text-color;
					line-height:50rpx;
				}
				.time{
					//display:none;
					float: right;
					font-size: $uni-font-size-sm;
					color: $uni-text-color-disable;
					line-height:50rpx;
				}
			}
		}
		.news{
			font-size: $uni-font-size-base;
			color: $uni-text-color-grey;
			line-height: 40rpx;
			//width: 100%;
			display: -webkit-box;
			-webkit-box-orient: vertical;
			-webkit-line-clamp: 1;
			overflow: hidden;
		}
	}
</style>

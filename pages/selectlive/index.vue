<template>
	<view>
		<view class="top">
		<image class="top-img" src="../../static/img/kaishi.png"></image>
		</view>
		<view class="zi">
			快来发起直播吧！
		</view>
		<view @click="open" class="but" style="bottom: 180rpx;">发起直播</view>
		<view @click="looklive" class="but">观看直播</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				
			}
		},
		methods:{
			open(){
				uni.navigateTo({
					url:'../live/index'
				})
			},
			looklive(){
				uni.navigateTo({
					url:'../pulllive/live'
				})
			}
		}
	}
</script>

<style>
	.top{
		/* position: relative; */
		width: 115px;
		height: 105px;
		position: absolute;
	    left:50%;
	    top:35%;
		transform: translate(-50%, -50%);
	
	}
	.top .top-img {
		width: 115px;
		height: 105px;
	}
	.zi {
		position: absolute;
		width:120;
		height:14px;
		font-size:14px;
		font-family:PingFang SC;
		font-weight:400;
		color:rgba(173,173,173,1);
		line-height:90px;
		left:50%;
		top:42%;
		transform: translate(-50%, -50%);
			
	}
	.but{
		position: absolute;
		position: fixed;
		bottom: 30rpx;
		line-height:50px;
		text-align: center;
		font-size: 30rpx;
		color: white;
		margin-left: 5%;
		width:90%;
		background:linear-gradient(-16deg,rgba(255,65,0,1),rgba(255,119,73,1));
		border-radius:25px;
		font-size:18px;
		font-family:PingFang SC;
		font-weight:400;
		/* color:rgba(255,255,255,1); */
	}

</style>

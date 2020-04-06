<template>
	<view>
		<view class="information">
			<view class="info">
				<image src="../../static/user1.jpg" class="face">
				</image>
				<view class="name">
					不愿透露姓名的皮卡皮卡
				</view>
			</view>
		</view>
		<view>
			<view class="mine">
				<view class="top">
					<view class="topTittle">
						我的游戏
					</view>
					<view class="more" @tap="tapMine">
						更多
					</view>
				</view>
				<view>
					<view class="gameInfo1" @tap="pic1dot1">
						<view>
							<image src="../../static/pics/xiaoshoupaihang1.jpg" class="gamePicture">
						</view>
						<view>
							Transport Fever 2
						</view>
					</view>
					<view class="gameInfo2" @tap="pic1dot2">
						<view>
							<image src="../../static/pics/xiaoshoupaihang2.jpg" class="gamePicture">
						</view>
						<view>
							勇者斗恶龙创世小玩家2
						</view>
					</view>
					<view class="line">
					</view>
				</view>
			</view>
			<view class="follow">
				<view class="top">
					<view class="topTittle">
						我的关注
					</view>
					<view class="more" @tap="tapFollow">
						更多
					</view>
				</view>
				<view>
					<view class="gameInfo1" @tap="pic2dot1">
						<view>
							<image src="../../static/pics/weinintuijian1.jpg" class="gamePicture">
						</view>
						<view>
							Counter-Strike
						</view>
					</view>
					<view class="gameInfo2" @tap="pic2dot2">
						<view>
							<image src="../../static/pics/weinintuijian2.jpg" class="gamePicture">
						</view>
						<view>
							PLAYERUNKNOWN'S…
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default 
	{
		data() 
		{
			return 
			{
				
			}
		},
		methods: 
		{
			tapMine()
			{
				uni.navigateTo({
					url: '../4-1/4-1',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			
			tapFollow()
			{
				uni.navigateTo({
					url: '../4-2/4-2',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			
			pic1dot1()
			{
				uni.navigateTo({
					url: '../gameinfo/gameinfo?gameid=1066780',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			
			pic1dot2()
			{
				uni.navigateTo({
					url: '../gameinfo/gameinfo?gameid=1072420',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			
			pic2dot1()
			{
				uni.navigateTo({
					url: '../gameinfo/gameinfo?gameid=730',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			
			pic2dot2()
			{
				uni.navigateTo({
					url: '../gameinfo/gameinfo?gameid=578080',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			}
		}
	}
</script>

<style>
	.information
	{
		width: 100%;
		height: 200rpx;
		background: #F0F0F0;
	}
	
	.face
	{
		width: 60px;
		height: 60px;
		border-radius: 50%;
		margin: 20px 30px 20px 50px;
	}
	
	.name
	{
		display: inline-block;
		font-size: 15px;
		/* border: 1px solid red; */
	}
	
	.face, .name
	{
		vertical-align: middle;
	}
	
	.topTittle
	{
		margin: 20rpx;
		float: left;
		display: block;
		font-size: 30rpx;
	}
	
	.more
	{
		margin: 20rpx;
		float: right;
		display: block;
		color: #666666;
	}
	
	.top
	{
		height: 100rpx;
		border: 1rpx transparent;
	}
	
	.gameInfo1, .gameInfo2
	{
		display: inline-block;
		margin: 0 auto;
		margin-left: 40rpx;
	}
	
	.gamePicture
	{
		width: 160px;
		height: 90px;
		display: inline-block;
	}
	
	.line
	{
		width: 90%;
		height: 1px;
		margin: 0 auto;
		border-top: solid #D8D8D8 1px;
	}
	
</style>

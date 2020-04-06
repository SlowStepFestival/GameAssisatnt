<template>
	<view class="content">
		<view class="title">
			{
				{title}
			}
		</view>
		<image class="images" :src="imageUrl">
		</image>
		<view class="tag">
			{
				{tag}
			}
		</view>
		<view class="gameIntro">
			游戏简介
		</view>
		<view class="introduction">
			{
				{introduction}
			}
		</view>
		<view class="timeRealease">
			{
				{timeRealease}
			}
		</view>
		
		<view class="buttonBox">
			<button class="gain" @tap="toGain">
				成就
			</button>
			<button class="discount">
				折扣
			</button>
			<button class="subscribe" @tap="onSub">
			{
				{subContent}
			}
			</button>
		</view>
		
		
	</view>
</template>
<script>
	export default 
	{
		onLoad(e) 
		{
			this.theGameID=e.gameid;
			console.log("注意这一条");
			console.log(this.theGameID);
			uni.request({
				url: 'http://47.103.206.26:8080/miniprogram/list/games?gameId='+e.gameid,
				method: 'GET',
				data: {},
				success: res => {
					console.log(res);
					this.title=res.data.gameList[0].name;
					this.imageUrl=res.data.gameList[0].imageUrl;
					this.introduction=res.data.gameList[0].introduction;
					this.timeRealease=res.data.gameList[0].releaseDate;
					this.tag=res.data.gameList[0].tag;
					console.log(this.timeRealease)
				},
				fail: () => {},
				complete: () => {}
			});
		},
		data() 
		{
			return 
			{
				theGameID:'';
				title:'';
				imageUrl:'';
				introduction:'';
				timeRealease:'';
				tag:'';
				subContent:'关注'
				
			}
		},
		methods: 
		{
			onSub()
			{
				if (this.subContent=='关注')
				{
					this.subContent='关注√';
				}
				else
				{
					this.subContent='关注';
				}
			},
			toGain()
			{
				uni.navigateTo({
					url: '../gain/gain?gameid='+this.theGameID,
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			}
		}
	}
</script>

<style>
.content
{
	display: flex;
	flex-direction: column;
}

.gameIntro
{
	font-size: 40upx;
}

.timeRealease
{
	margin-bottom: 20upx;
}

.title
{
	text-align: center;
	font-size:40upx;
	margin-bottom: 0upx;
	border-bottom: 5upx solid #000000;

}

.images
{
	margin-top: 5upx;
	margin-bottom: 5upx;
	border-bottom: 5upx solid #000000;
	margin: 0 auto;
	width: 95%;
}

.tag{
	color: #DD524D;
}

.introduction
{
}

.buttonBox
{
	display: flex;
	flex-direction: row;
	font-size: 40px;

}

page
{
	background:#EEEEEE;
}

</style>

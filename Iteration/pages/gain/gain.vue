<template>
	<view>
		<view class="title">
			成就列表
		</view>
		
		
		<view class="uni-list">
			<view class="uni-list-cell" hover-class="uni-list-cell-hover" v-for="(item,index) in list" :key="index">
				<view class="uni-media-list">
					<image class="uni-media-list-logo" :src="item.imageUrl">
					</image>
					<view class="uni-media-list-body">
						<view class="uni-media-list-text-top">
							{
								{item.achievementName}
							}
						</view>
						<view class="uni-media-list-text-bottom uni-ellipsis">
							{
								{item.profile}
							}
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
		onLoad(e) 
		{
			uni.request({
				url: 'http://47.103.206.26:8080/miniprogram/list/achievements?gameId='+e.gameid,
				method: 'GET',
				data: {},
				success: res => {
					this.list=res.data.achievementList;
					console.log(this.list)
				},
				fail: () => {},
				complete: () => {}
			});
		},
		data() 
		{
			return 
			{
				list:[]
			}
		},
		methods: {
			
		}
	}
</script>

<style>
.title
{
	text-align: center;
	font-size:40upx;
	margin-bottom: 0upx;
	border-bottom: 5upx solid #000000;
}
	
	
	.uni-media-list-body
	{
		height:auto;
	}
	.uni-media-list-text-top
	{
	}
	
	.inv-h-w
	{
		height: 80upx;
		display: flex;
	}
	.inv-h
	{
		font-size: 30upx;
		flex: 1;
		text-align: center;
		color:#D8D8D8;
		height: 80upx;
		line-height: 80upx;
	}
	.inv-h-se
	{
		color: #000000;
		border-bottom: 1upx solid #000000
	}

</style>

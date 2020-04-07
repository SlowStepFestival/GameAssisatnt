<template>
	<view>
		<view class="title">
			我的关注
		</view>
		
		<view class="uni-list">
			<view class="uni-list-cell" hover-class="uni-list-cell-hover" v-for="(item,index) in gamelist1" :key="index"
			@tap="opengameinfo" :data-gameid="item.gameId">
				<view class="uni-media-list">
					<image class="uni-media-list-logo" :src="item.logoUrl">
					</image>
					<view class="uni-media-list-body">
						<view class="uni-media-list-text-top">
							{{item.name}}
						</view>
						<view class="uni-media-list-text-bottom uni-ellipsis">
							售价：{{item.price}}
							</view>
						<view class="discount">
							折扣：{{item.discount}}
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
		data() {
			return {
				gamelist1:[]
			}
		},
		onLoad:function()
		{
			uni.request({
				url: 'http://47.103.206.26:8080/miniprogram/list/hot/games',
				method: 'GET',
				data: {},
				success: res => {
					this.gamelist1=res.data.gameList;
				},
				fail: () => {},
				complete: () => {}
			});
		},
		methods: 
		{
			opengameinfo(e){
				var gameid=e.currentTarget.dataset.gameid;
				uni.navigateTo({
					url: '../gameinfo/gameinfo?gameid='+gameid
				}
				
				);
			},
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
</style>

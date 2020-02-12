<template>
	<view>
		<componentSearchBar isnavigator="true"></componentSearchBar>
		<view>
			<view class="uni-padding-wrap">
				<view class="page-section swiper">
					<view class="page-section-spacing">
						<swiper class="swiper" autoplay indicator-dots circular interval = "3000">
							<swiper-item>
								<view class="swiper-item1" @tap="pic1dot1"><image mode = "widthFix" src="../../static/pictures/recommend1.jpg"></view>
							</swiper-item>
							<swiper-item>
								<view class="swiper-item2" @tap="pic2dot1"><image mode = "widthFix" src="../../static/pictures/recommend2.jpg"></view>
							</swiper-item>
							<swiper-item>
								<view class="swiper-item3" @tap="pic3dot1"><image mode = "widthFix" src="../../static/pictures/recommend3.jpg"></view>
							</swiper-item>
						</swiper>
					</view>
				</view>
			</view>
		</view>
		<view>
			<view class="classification" >
				<view class="type1" @tap="on3dot1"><image mode="widthFix" src="../../static/iconType/1.png" class="iconType1">
					<view>为您推荐</view>
				</view>
				<view class="type2" @tap="on3dot2"><image mode="widthFix" src="../../static/iconType/2.png" class="iconType2">
					<view>活动促销</view>
				</view>
				<view class="type3" @tap="on3dot3"><image mode="widthFix" src="../../static/iconType/3.png" class="iconType3">
					<view>销量排行</view>
				</view>
				<view class="type4" @tap="on3dot4"><image mode="widthFix" src="../../static/iconType/4.png" class="iconType4">
					<view>最新上架</view>
				</view>
			</view>
		</view>
		<view>
			<view class="recommendation">
				<view class="top">
					<view class="topTittle">为您推荐</view>
					<view class="more" @tap="tapRecommendation">更多</view>
				</view>
				<view>
					<view class="gameInfo1" @tap="pic1dot1">
						<view>
							<image src="../../static/pics/weinintuijian1.jpg" class="gamePicture">
						</view>
						<view>Counter-Strike</view>
					</view>
					<view class="gameInfo2" @tap="pic1dot2">
						<view>
							<image src="../../static/pics/weinintuijian2.jpg" class="gamePicture">
						</view>
						<view>PLAYERUNKNOWN'S…</view>
					</view>
					<view class="line"></view>
				</view>
			</view>
			<view class="activity">
				<view class="top">
					<view class="topTittle">活动促销</view>
					<view class="more" @tap="tapActivity">更多</view>
				</view>
				<view>
					<view class="gameInfo1" @tap="pic2dot1">
						<view>
							<image src="../../static/pics/huodongcuxiao1.jpg" class="gamePicture">
						</view>
						<view>Jurassic World…</view>
					</view>
					<view class="gameInfo2" @tap="pic2dot2">
						<view>
							<image src="../../static/pics/huodongcuxiao2.jpg" class="gamePicture">
						</view>
						<view>DRAGON BALL…</view>
					</view>
					<view class="line"></view>
				</view>
			</view>
			<view class="sales">
				<view class="top">
					<view class="topTittle">销售排行</view>
					<view class="more" @tap="TapSales">更多</view>
				</view>
				<view>
					<view class="gameInfo1" @tap="pic3dot1">
						<view>
							<image src="../../static/pics/xiaoshoupaihang1.jpg" class="gamePicture">
						</view>
						<view>Transport Fever 2</view>
					</view>
					<view class="gameInfo2" @tap="pic3dot2">
						<view>
							<image src="../../static/pics/xiaoshoupaihang2.jpg" class="gamePicture">
						</view>
						<view>勇者斗恶龙创世小玩家2</view>
					</view>
					<view class="line"></view>
				</view>
			</view>
			<view class="new">
				<view class="top">
					<view class="topTittle">最新上架</view>
					<view class="more" @tap="tapNew">更多</view>
				</view>
				<view>
					<view class="gameInfo1" @tap="pic1dot1">
						<view>
							<image src="../../static/pics/weinintuijian1.jpg" class="gamePicture">
						</view>
						<view>Counter-Strike</view>
					</view>
					<view class="gameInfo2" @tap="pic1dot2">
						<view>
							<image src="../../static/pics/weinintuijian2.jpg" class="gamePicture">
						</view>
						<view>PLAYERUNKNOWN'S…</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import componentSearchBar from "../../components/searchbar/searchbar.vue";
	export default {
		data() {
			return {
				background: ['color1', 'color2', 'color3'],
				            indicatorDots: true,
				            autoplay: true,
				            interval: 2000,
				            duration: 500
			}
		},
		components:{
				componentSearchBar
			},
		methods: {
			on3dot1(){
				uni.navigateTo({
					url: '../3-1/3-1',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			on3dot2(){
				uni.navigateTo({
					url: '../3-2/3-2',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			on3dot3(){
				uni.navigateTo({
					url: '../3-3/3-3',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			on3dot4(){
				uni.navigateTo({
					url: '../3-4/3-4',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			tapRecommendation(){
				uni.navigateTo({
					url: '../3-1/3-1',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			tapActivity(){
				uni.navigateTo({
					url: '../3-2/3-2',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			TapSales(){
				uni.navigateTo({
					url: '../3-3/3-3',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			tapNew(){
				uni.navigateTo({
					url: '../3-4/3-4',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			pic1dot1(){
				uni.navigateTo({
					url: '../gameinfo/gameinfo?gameid=730',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			pic1dot2(){
				uni.navigateTo({
					url: '../gameinfo/gameinfo?gameid=578080',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			pic2dot1(){
				uni.navigateTo({
					url: '../gameinfo/gameinfo?gameid=648350',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			pic2dot2(){
				uni.navigateTo({
					url: '../gameinfo/gameinfo?gameid=454650',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			pic3dot1(){
				uni.navigateTo({
					url: '../gameinfo/gameinfo?gameid=1066780',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			pic3dot2(){
				uni.navigateTo({
					url: '../gameinfo/gameinfo?gameid=1072420',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			}
		}
	}
</script>

<style>
	
	swiper{
	  width: 100%;
	  height: 180px;
	}
	
	image{
	  width: 100%;
	}
	
	.classification{
		align-content: center;
		padding: 20rpx 20rpx 20rpx 20rpx;
		font-size: 25px;
		color: #666666;
		text-align: center;
		margin:0 auto
	}
	
	.type1, .type2, .type3, .type4{
		width: 25%;
		display: inline-block;
	}
	
	.iconType1, .iconType2, .iconType3, .iconType4{
		width: 75rpx;
		display: flex;
		margin: 0 auto;
	}
	
	.topTittle{
		margin: 20rpx;
		float: left;
		display: block;
		font-size: 30rpx;
	}
	
	.more{
		margin: 20rpx;
		float: right;
		display: block;
		color: #666666;
	}
	
	.top{
		height: 100rpx;
		border: 1rpx transparent;
	}

	
	.gameInfo1, .gameInfo2{
		display: inline-block;
		margin: 0 auto;
		margin-left: 40rpx;
	}
	
	.gamePicture{
		width: 160px;
		height: 90px;
		display: inline-block;
	}
	
	.line{
		width: 90%;
		height: 1px;
		margin: 0 auto;
		border-top: solid #D8D8D8 1px;
	}
</style>

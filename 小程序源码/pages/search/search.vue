<template>
	<view>
		<componentSearchBar isnavigator="false" @searchinput="onSearchInputEvent"></componentSearchBar>
		<view class="uni-list">
			<view class="uni-list-cell" hover-class="uni-list-cell-hover" v-for="(item,index) in searchGameList" :key="index"
			@tap="opengameinfo" :data-gameid="item.gameId">
				<view class="uni-media-list">
					<image class="uni-media-list-logo" :src="item.logoUrl"></image>
					<view class="uni-media-list-body">
						<view class="uni-media-list-text-top">{{item.name}}</view>
						<view class="uni-media-list-text-bottom uni-ellipsis">{{item.price}}</view>
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
				searchGameList:[]
			}
		},
		components:{
				componentSearchBar
			},
		methods: {
			onSearchInputEvent:function(event){
				console.log(event)
				uni.request({
					url:'http://47.103.206.26:8080/miniprogram/list/games?name='+event,
					method:'GET',
					data:{},
					success:res=>{
						console.log(res);
						this.searchGameList=res.data.gameList;
					},
					fail:()=>{
						console.log("失败")
					}
				})
			},
			opengameinfo(e){
				var gameid=e.currentTarget.dataset.gameid;
				uni.navigateTo({
					url: '../gameinfo/gameinfo?gameid='+gameid
				});
				
			}
		}
	}
	
</script>

<style>
	
</style>

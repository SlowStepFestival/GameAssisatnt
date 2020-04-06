<template>
	<view>
		<componentSearchBar isnavigator="true">
		</componentSearchBar>
	
		<view class="uni-padding-wrap">
	        <view class="page-section swiper">
	            <view class="page-section-spacing">
	                <swiper class="swiper" autoplay indicator-dots circular interval = "3000">
	                    <swiper-item>
	                            <view class="swiper-item ">
									<image mode = "widthFix" src="../../static/2.jpg" >
									</image>
								</view>
	                    </swiper-item>
	                    <swiper-item>
	                            <view class="swiper-item ">
									<image mode = "widthFix" src="../../static/test1.jpg" >
									</image>
								</view>
	                    </swiper-item>
	                    <swiper-item>
	                            <view class="swiper-item ">
									<image mode = "widthFix" src="../../static/test2.jpg" >
									</image>
								</view>
	                    </swiper-item>
	                    </swiper>
	                </view>
	        </view>
		</view>
		
		
		
		<view class="content">
			<view class="uni-list">
				<view class="uni-list-cell" hover-class="uni-list-cell-hover" v-for="(item,index) in news" :key="index"
				@tap="openInfo" :data-newsid="item.post_id">
					<view class="uni-media-list">
						<image class="uni-media-list-logo" :src="item.author_avatar">
						</image>
						<view class="uni-media-list-body">
							<view class="uni-media-list-text-top">{{item.title}}
							</view>
							<view class="uni-media-list-text-bottom uni-ellipsis">{{item.content}}
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
	
</template>

<script>
	import componentSearchBar from "../../components/searchbar/searchbar.vue";
	export default 
	{
		data() 
		{
			return 
			{
			    background: ['color1', 'color2', 'color3'];
			    indicatorDots: true;
			    autoplay: true;
			    interval: 2000;
			    duration: 500;
				news:[]
			}
		},
		onLoad() 
		{
			// uni.request({
			// 	url: 'https://unidemo.dcloud.net.cn/api/news',
			// 	method: 'GET',
			// 	data: {},
			// 	success: res => {
			// 		console.log(res);
			// 		this.news = res.data;
			// 	},
			// 	fail: () => {},
			// 	complete: () => {}
			// });
			
			this.news = [
				{
					author_avatar: "../../static/page1.jpg",
					post_id:1,
					title:"深夜聊天室：你对Xbox新主机有着怎样的期待？",
					content:"在今日的TGA 2019 颁奖典礼上，微软公布了Xbox新主机“X系列”，其立方体的造型非常抢眼，随后多家媒体也曝光了这款新主机的性能及特点。"
				},
				{
					author_avatar: "../../static/page2.jpg",
					post_id:2,
					title:"《冰汽时代》前传DLC“最后的秋天”预告片：2020年1月21日登陆PC",
					content:"目前此DLC已上架Steam商店，据介绍，《最后的秋天》讲述了发生在冰汽时代末日世界降临之前的一系列事件。本前传式DLC包括了全新的剧情和游戏机制、独特建筑、以及深入冰汽时代世界的支线情节与故事。《最后的秋天》讲述了发生在113号工地的一连串事件，以及在大地被冰封之前工程师们试图造出能量塔的努力。本扩展包包含全新的环境、法律之书、独特的科技以及一系列新建筑，让玩家以不同的方式去打造社会与城市。你将率领一群工程师去试图建造出工程技术的奇迹——能量塔。这将考验你应对极端情形的能力。作为113号工地的领袖，你需要在期盼奇迹的同时做好最坏的打算。为了女王和国家！《最后的秋天》特色：·发生在即将来袭的毁灭性严寒之前的剧情·掌握全新法律之书，以前所未有的方式打造社会与城市·建造多种新建筑·发现由蒸汽驱动的神奇技术·活用更高阶的策略生存下去·探索尚未被冰雪覆盖的美丽环境。同时，本DLC包含在《冰汽时代》8月份在Stema发布的季票之内。季票内容除了/大地裂缝/、/最后的秋天”在外，还有尚待揭晓的“TVADGYCGJR计划”。"
				},
				{
					author_avatar: "../../static/page3.jpg",
					post_id:3,
					title:"FS社《只狼：影逝二度》获奖感言：衷心感谢玩家、请保持期待",
					content:"《只狼：影逝二度》斩获了TGA年度游戏，FromsoftWare官方推特也发文表达了对玩家的感谢之情。并承诺会“竭力创造能提供体验新鲜而又耐人寻味的游戏”，并且真诚地希望玩家期待他们筹备中的未来作品。未来作品中自然会包含今年公布的《Elden Ring》，比较遗憾的是，虽然此前一些坊间传闻声称TGA上会出现这部作品，但最后并没有亮相。今年已接近尾声，但即使是对一些国外的爆料人而言，目前得到的消息仍然很零碎。或许与之前各种原始玩法的泄露有关，保密工作似乎更加严实了。今年或许很难再看到游戏的官方信息，在近期发售似乎也是更加难以指望的事了。"
				},
				{
					author_avatar: "../../static/page4.jpg",
					post_id:4,
					title:"生化危机2：重制版》试玩版重回PS Store 官方暗示有新内容",
					content:"CapcomAsia官方微博发布消息，《生化危机2：重制版》试玩重回PS Store，本次能不限时间地体验早期剧情，还可能有新的发现……？官方的语气很明显是在暗示着什么，看来游戏的早期剧情中还隐藏着什么等待玩家们的发现。而官方微博下方评论中的网友反映，PS4版游戏更新了一个奖杯，而这个奖杯内容与之前Steam版显现的新成就的内容也是一致的。看来这个彩蛋的神秘面纱已经近在眼前，就等大家在游戏中将它揭开啦。"
				},
				{
					author_avatar: "../../static/page6.jpg",
					post_id:5,
					title:"GN评《凤凰点》7分：想法很棒、但需要微调和平衡",
					content: " IGN对由《幽浮》之父Julian Gollop率领团队打造的回合制策略游戏《凤凰点》进行了评测，并打出了7分的评价。评测者认为《凤凰点》的想法很棒，但大多数处于一种实验的状态，需要进一步平衡和调整。《凤凰点》有很多有趣的想法，可以为回合制策略游戏的复兴做出贡献，但是其中许多内容都需要改进和平衡。 处理派系关系和限制敌方各个身体部位之类的设计非常好，并且可以在复杂性与库存管理之间取得很好的平衡。 同时，在任务多样化和基地建设等一些方面，它表现得很糟糕。游戏后期梦呓谵妄指数的突然上涨非常严重且不平衡，再加上缺乏打磨，《凤凰点》仍处于一种实验性且未经改进的状态。但是可以肯定的是，这是一个有趣的实验。"
				},
				{
					author_avatar: "../../static/page5.jpg",
					post_id:6,
					title:"《模拟人生4》添“儿童雕像” 神似“尤达宝宝”有点可怕",
					content: "据Polygon报道，《模拟人生4》最近的更新加入了一个长得和“尤达宝宝”神似的雕像物品，名叫“儿童雕像”，售价504模拟币。官方在描述中承认，该雕像的形象确实是参考了星战真人剧《曼达洛人》中的“尤达宝宝”。"			
				},
				{
					author_avatar: "../../static/page7.jpg",
					post_id:7,
					title:"《空洞骑士：丝绸之歌》OST试听 悠扬弦乐余音绕梁",
					content: "TEAM CHERRY在官网公布了《空洞骑士：丝绸之歌》的更新，并且发布了两首游戏OST的试听。游戏的完整原声集将包括30首曲目，并且对弦乐会更加侧重。	在更新日志中，他们提到这是一部非常大型（Very Large）的游戏，并且他们会尽全力完成所有承诺的要素。在新敌人方面，他们此前承诺会加入150+的新敌人，而他们现在认为那个估计太保守了，虽然目前不清楚最终会有多少新敌人，不过他们现在给出了编号163、164、165的敌人。不过他们也不会漫无目的地加入新内容，而是会根据剧情的呈现，塑造出探索一个广阔而惊艳新世界的体验。"
				},
				{
					author_avatar: "../../static/page8.jpg",
					post_id:8,
					title:"《永劫无间》更多信息：筹备登陆主机、付费买断制",
					content: "今天在TGA公布的国产游戏《永劫无间》官方微博公布了关于游戏的更多信息，一起来看看吧。	嗨，我们是24 Entertainment，关于《永劫无间》，这还有些信息：登录平台——2020年登陆PC平台，Steam商店页现已上线；主机平台筹备中。付费模式——本体付费买断.预告片中的战斗——弹刀的触发基于多人战斗逻辑，加之为鼓励进攻没有防御键。这部分的体验，眼见不一定为实。而飞索，任何地点、敌人均可瞄作目标，并有不同的进一步交互。更多的解释也好说明也罢，先按下了.今天只匆匆一瞥，产品进度飞速进行，开发胜于声明.未来的日子里，你们负责期待，鞭挞，用力.我们且砥砺前行"
				},
				{
					author_avatar: "../../static/page9.jpg",
					post_id:9,
					title:"Gearbox&Counterplay Games新作《神陨》(God Fall)专访：海量游戏情报 会充分利用PS5",
					content: ",Gearbox&Counterplay Games新作《神陨》(God Fall)专访：海量游戏情报 会充分利用PS5",
				},
				{
					author_avatar: "../../static/page10.jpg",
					post_id:10,
					title:"《无双大蛇3：终极版》将追加特典服装 周瑜、妲己在列",
					content: "光荣特库摩宣布，战术动作游戏「无双OROCHI 蛇魔」系列最新作『无双大蛇3：终极版』（PlayStation®4／Nintendo Switch™／Steam®）",
				},
				{
					author_avatar: "../../static/page11.jpg",
					post_id:11,
					title:"《三国志14》剧本“黄巾之乱”介绍：汉朝灭亡关键",
					content: "光荣特库摩官博这周开始介绍《三国志14》严选的剧本，今日带来了“黄巾之乱”的介绍，一起来了解一下。",
				},
				{
					author_avatar: "../../static/page12.jpg",
					post_id:12,
					title:"《武士模拟器》（Samurai Simulator）上架Steam 2020年发售支持中文",
					content: "由Game Hunters 制作、发行的模拟游戏《武士模拟器》（Samurai Simulator）上架Steam，预计于2020年第四季度推出，支持简体中文，游戏中玩家将体验日本武士的一生。",
				}
				
				];
		},
		components:
		{
			componentSearchBar
		},
		methods: 
		{
			changeIndicatorDots(e) {
			            this.indicatorDots = !this.indicatorDots
			        },
			changeAutoplay(e) {
			            this.autoplay = !this.autoplay
			        },
			intervalChange(e) {
			            this.interval = e.target.value
			        },
			durationChange(e) {
			            this.duration = e.target.value
			        },
			openInfo(e){
				
				var newsid = e.currentTarget.dataset.newsid;
				console.log(newsid);
				uni.navigateTo({
					url: '../info/info?newsid='+newsid
				});
				
			}
		}
	}
</script>

<style>
	swiper
	{
	  width: 100%;
	  height: 180px;
	}
	
	image
	{
	  width: 100%;
	}
	
	.searchbar
	{
		background-color: #000000;
		padding: 20rpx;
	}
	.search-navigator
	{
		width: 100%;
		height: 60rpx;
		background-color: #FFFFFF;
		border-radius: 10rpx;
		background-image: url("data:image/png;base64,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");
		background-position: left;
		background-repeat: no-repeat;
		background-size:6%;
	}

	.uni-media-list-body
	{
		height:auto;
	}
	
	.uni-media-list-text-top
	{
		line-height: 1.4em;
	}
	
	.uni-media-list-logo
	{
		width: 200upx;
		height: 140upx;
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

<template>
	<view class="content">
		
		<view class="inv-h-w">
			<view :class="['inv-h',Inv==1?'inv-h-se' :'']" @click="Inv=1" >正文</view>
			<view :class="['inv-h',Inv==2?'inv-h-se' :'']" @click="getComments" >评论</view>
		</view>
		
		<view class="page1" v-show="Inv==1">
			<image :src="imgurl" mode="widthFix" class="img"></image>
			<view class="title">{{title}}</view>
			<view class="art-content">
				<rich-text class="richText" :nodes="strings"></rich-text>
			</view>
			
			<view class="uni-form-item holdButton ">
			                <input class="uni-input commentInput" focus placeholder="输入评论" />
							<image class="goodImg" src="../../static/good.png" mode=""  v-show="good==0"  @tap="good==1"></image>
							<image class="goodImg" src="../../static/comments.png" mode="" ></image>
							<!-- <button class="commentButton"   type="default" size="mini">评论</button> -->
			</view>
		</view>
			
		<view class="page2" v-show="Inv==2">
			<view class="uni-list">
				<view class="uni-list-cell" hover-class="uni-list-cell-hover" v-for="(item,index) in commentsList" :key="index"
				@tap="opengameinfo" :data-gameid="item.gameId">
					<view class="uni-media-list">
						<image class="uni-media-list-logo commentImg" :src="item.userImage"></image>
						<view class="uni-media-list-body">
							<view class="uni-media-list-text-top">{{item.username}}</view>
							<view class="uni-media-list-text-bottom uni-ellipsis">{{item.content}}</view>
							<view class="discount">{{item.content}}</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		
		
		
		
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title:'',
				strings:'',
				imgurl:'',
				Inv:1,
				commentsList:[],
				good:0,
				news:[]
			}
		},
		onLoad(e) {
			console.log(e);
			
			this.news = [{},
				{author_avatar: "../../static/page1.jpg",
				post_id:1,
				title:"深夜聊天室：你对Xbox新主机有着怎样的期待？",
				content:"</br>在今日的TGA 2019 颁奖典礼上，微软公布了Xbox新主机“X系列”，其立方体的造型非常抢眼，随后多家媒体也曝光了这款新主机的性能及特点。</br></br>"
				},
				{author_avatar: "../../static/page2.jpg",
				post_id:2,
				title:"《冰汽时代》前传DLC“最后的秋天”预告片：2020年1月21日登陆PC",
				content:"<p>目前此DLC已上架Steam商店，据介绍，《最后的秋天》讲述了发生在冰汽时代末日世界降临之前的一系列事件。</p>  <p><br></br>本前传式DLC包括了全新的剧情和游戏机制、独特建筑、以及深入冰汽时代世界的支线情节与故事。</p></br><p>《最后的秋天》讲述了发生在113号工地的一连串事件，以及在大地被冰封之前工程师们试图造出能量塔的努力。本扩展包包含全新的环境、法律之书、独特的科技以及一系列新建筑，让玩家以不同的方式去打造社会与城市。你将率领一群工程师去试图建造出工程技术的奇迹——能量塔。这将考验你应对极端情形的能力。作为113号工地的领袖，你需要在期盼奇迹的同时做好最坏的打算。为了女王和国家！</p></br></br></br><p>《最后的秋天》特色：·发生在即将来袭的毁灭性严寒之前的剧情·掌握全新法律之书，以前所未有的方式打造社会与城市·建造多种新建筑·发现由蒸汽驱动的神奇技术·活用更高阶的策略生存下去·探索尚未被冰雪覆盖的美丽环境。</p></br></br></br><p>同时，本DLC包含在《冰汽时代》8月份在Stema发布的季票之内。季票内容除了/大地裂缝/、/最后的秋天”在外，还有尚待揭晓的“TVADGYCGJR计划”。</br></br></br></p>"
				},
				{author_avatar: "../../static/page3.jpg",
				post_id:3,
				title:"FS社《只狼：影逝二度》获奖感言：衷心感谢玩家、请保持期待",
				content:"《只狼：影逝二度》斩获了TGA年度游戏，FromsoftWare官方推特也发文表达了对玩家的感谢之情。并承诺会“竭力创造能提供体验新鲜而又耐人寻味的游戏”，并且真诚地希望玩家期待他们筹备中的未来作品。未来作品中自然会包含今年公布的《Elden Ring》，比较遗憾的是，虽然此前一些坊间传闻声称TGA上会出现这部作品，但最后并没有亮相。今年已接近尾声，但即使是对一些国外的爆料人而言，目前得到的消息仍然很零碎。或许与之前各种原始玩法的泄露有关，保密工作似乎更加严实了。今年或许很难再看到游戏的官方信息，在近期发售似乎也是更加难以指望的事了。"
				},
				{author_avatar: "../../static/page4.jpg",
				post_id:4,
				title:"生化危机2：重制版》试玩版重回PS Store 官方暗示有新内容",
				content:"CapcomAsia官方微博发布消息，《生化危机2：重制版》试玩重回PS Store，本次能不限时间地体验早期剧情，还可能有新的发现……？官方的语气很明显是在暗示着什么，看来游戏的早期剧情中还隐藏着什么等待玩家们的发现。而官方微博下方评论中的网友反映，PS4版游戏更新了一个奖杯，而这个奖杯内容与之前Steam版显现的新成就的内容也是一致的。看来这个彩蛋的神秘面纱已经近在眼前，就等大家在游戏中将它揭开啦。"
				},
				{author_avatar: "../../static/page6.jpg",
				post_id:5,
				title:"GN评《凤凰点》7分：想法很棒、但需要微调和平衡",
				content: " IGN对由《幽浮》之父Julian Gollop率领团队打造的回合制策略游戏《凤凰点》进行了评测，并打出了7分的评价。评测者认为《凤凰点》的想法很棒，但大多数处于一种实验的状态，需要进一步平衡和调整。《凤凰点》有很多有趣的想法，可以为回合制策略游戏的复兴做出贡献，但是其中许多内容都需要改进和平衡。 处理派系关系和限制敌方各个身体部位之类的设计非常好，并且可以在复杂性与库存管理之间取得很好的平衡。 同时，在任务多样化和基地建设等一些方面，它表现得很糟糕。游戏后期梦呓谵妄指数的突然上涨非常严重且不平衡，再加上缺乏打磨，《凤凰点》仍处于一种实验性且未经改进的状态。但是可以肯定的是，这是一个有趣的实验。"
				},
				{author_avatar: "../../static/page5.jpg",
				post_id:6,
				title:"《模拟人生4》添“儿童雕像” 神似“尤达宝宝”有点可怕",
				content: "据Polygon报道，《模拟人生4》最近的更新加入了一个长得和“尤达宝宝”神似的雕像物品，名叫“儿童雕像”，售价504模拟币。官方在描述中承认，该雕像的形象确实是参考了星战真人剧《曼达洛人》中的“尤达宝宝”。"			
				},
				{author_avatar: "../../static/page7.jpg",
				post_id:7,
				title:"《空洞骑士：丝绸之歌》OST试听 悠扬弦乐余音绕梁",
				content: "TEAM CHERRY在官网公布了《空洞骑士：丝绸之歌》的更新，并且发布了两首游戏OST的试听。游戏的完整原声集将包括30首曲目，并且对弦乐会更加侧重。	在更新日志中，他们提到这是一部非常大型（Very Large）的游戏，并且他们会尽全力完成所有承诺的要素。在新敌人方面，他们此前承诺会加入150+的新敌人，而他们现在认为那个估计太保守了，虽然目前不清楚最终会有多少新敌人，不过他们现在给出了编号163、164、165的敌人。不过他们也不会漫无目的地加入新内容，而是会根据剧情的呈现，塑造出探索一个广阔而惊艳新世界的体验。"
				},
				{author_avatar: "../../static/page8.jpg",
				post_id:8,
				title:"《永劫无间》更多信息：筹备登陆主机、付费买断制",
				content: "今天在TGA公布的国产游戏《永劫无间》官方微博公布了关于游戏的更多信息，一起来看看吧。	嗨，我们是24 Entertainment，关于《永劫无间》，这还有些信息：登录平台——2020年登陆PC平台，Steam商店页现已上线；主机平台筹备中。付费模式——本体付费买断.预告片中的战斗——弹刀的触发基于多人战斗逻辑，加之为鼓励进攻没有防御键。这部分的体验，眼见不一定为实。而飞索，任何地点、敌人均可瞄作目标，并有不同的进一步交互。更多的解释也好说明也罢，先按下了.今天只匆匆一瞥，产品进度飞速进行，开发胜于声明.未来的日子里，你们负责期待，鞭挞，用力.我们且砥砺前行"
				},
				{author_avatar: "../../static/page9.jpg",
				post_id:9,
				title:"Gearbox&Counterplay Games新作《神陨》(God Fall)专访：海量游戏情报 会充分利用PS5",
				content: ",Gearbox&Counterplay Games新作《神陨》(God Fall)专访：海量游戏情报 会充分利用PS5",
				},
				{author_avatar: "../../static/page10.jpg",
				post_id:10,
				title:"《无双大蛇3：终极版》将追加特典服装 周瑜、妲己在列",
				content: "光荣特库摩宣布，战术动作游戏「无双OROCHI 蛇魔」系列最新作『无双大蛇3：终极版』（PlayStation®4／Nintendo Switch™／Steam®）",
				},
				{author_avatar: "../../static/page11.jpg",
				post_id:11,
				title:"《三国志14》剧本“黄巾之乱”介绍：汉朝灭亡关键",
				content: "光荣特库摩官博这周开始介绍《三国志14》严选的剧本，今日带来了“黄巾之乱”的介绍，一起来了解一下。",
				},
				{author_avatar: "../../static/page12.jpg",
				post_id:12,
				title:"《武士模拟器》（Samurai Simulator）上架Steam 2020年发售支持中文",
				content: "由Game Hunters 制作、发行的模拟游戏《武士模拟器》（Samurai Simulator）上架Steam，预计于2020年第四季度推出，支持简体中文，游戏中玩家将体验日本武士的一生。",
				}
				
			];
			
			// uni.request({
			// 	url: 'https://unidemo.dcloud.net.cn/api/news/36kr/'+e.newsid,
			// 	method: 'GET',
			// 	data: {},
			// 	success: res => {
			// 		console.log(res);
			// 		this.title = res.data.title;
			// 		this.strings = res.data.content;
			// 		this.imgurl = res.data.author_avatar;
			// 	},
			// 	fail: () => {},
			// 	complete: () => {}
			// });
			
			var pageData =  this.news[e.newsid];
			this.title = pageData.title; 
			this.strings = pageData.content;
			this.imgurl = pageData.author_avatar;
		},
		methods: {
			getComments(e){
				// uni.request({
				// 	url: '',
				// 	method: 'GET',
				// 	data: {},
				// 	success: res => {},
				// 	fail: () => {},
				// 	complete: () => {}
				// });
				this.Inv=2;
				var list = [];
				
				list = [{username:"12-13 23:39 梦逝魂殇",
						content:"在国内 不用多说 也不用咋宣传 PC至上的国度没有独占买的人很不会很多 喜欢的自然会买 xbox的大头也一直都是欧美市场 看评论各种冷嘲热讽 心疼X系列 还没出在游民几乎判了死刑 别人微软自己掏钱做游戏争取让更多人玩到 结果反因为这点被当笑料 哎",
						userImage:"../../static/user1.jpg"
						},
						{username:"今日 17:27 咩天狗",
						content:"动视：这俩月怎么没人骂我了？",
						userImage:"../../static/user2.jpg"
						},
						{username:"今日17:12 反喷组",
						content:"不要叫腾讯看见这条新闻",
						userImage:"../../static/user3.jpg"
						},
						{username:"19分钟前 huiop2",
						content:"这个引战手法太低端，差评。",
						userImage:"../../static/user4.jpg"
						},
						{username:"11-13 小猫咪",
						content:"当时索尼买了内容优先发行权，想在ps4某期再榨一笔，虽然人家花钱了理所应当、商业竞争，但这种行为不论绿蓝两派都挺恶心人。",
						userImage:"../../static/user5.jpg"
						},
						{username:"11-13 奔流河",
						content:"当时索尼买了内容优先发行权，想在ps4某期再榨一笔，虽然人家花钱了理所应当、商业竞争，但这种行为不论绿蓝两派都挺恶心人。",
						userImage:"../../static/user6.jpg"
						}
							
						];
				this.commentsList =  list;
				console.log(this.commentsList);
			}
		}
	}
</script>

<style>
	.content{padding: 10upx 2%; width: 96%;flex-wrap: wrap;}
	.title{line-height: 2.2em; font-weight: 800; height: 120upx}
	.art-content{line-height: 1.8em;}
	.img{
		width:100%;
	}
	.inv-h-w{height: 80upx;display: flex;}
	.inv-h{font-size: 30upx;flex: 1;text-align: center;color:#D8D8D8;height: 80upx;line-height: 80upx;}
	.inv-h-se{color: #000000;border-bottom: 1upx solid #000000}

	.holdButton{
		width: 100%;
		left:0;
		background-color: #F0F0F0;
		position: fixed;
			bottom: 0px;
	}
	.goodImg{
		width: 60upx;
		height: 60upx;
		margin: 10upx;
	}
	.commentInput{
		width: 250upx;
	}

	.commentImg{
		width: 80upx;
		height: 80upx;
		border-radius: 40upx;
	}
</style>

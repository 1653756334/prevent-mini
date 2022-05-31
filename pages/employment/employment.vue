<template>
	<view class="employment">
		<view class="topBar">
			<image class="topIcon" src="../../static/home.png"></image>
			<view class="title">
				“遇贫则鸣”防返贫平台
			</view>
		</view>
		<view class="banner">
			<image src="../../static/banner.jpg"></image>
		</view>
		<view class="services">
			<view class="disc">就业帮扶</view>
			<view class="serviceWrap">
				<view class="item" v-for="item in serviceItems" :key="item.imgUrl">
					<view class="imgOuter">
						<image :src="item.imgUrl"></image>
					</view>
					<view class="serviceTitle">
						{{item.title}}
					</view>
				</view>
			</view>
		</view>
		<view class="news">
			<view class="newsTitle">
				<view class="bold">就业要闻</view>
				<view class="">查看全部</view>
			</view>
			<view class="newsContent">
				<view class="emptyNews" v-if="newsDtail.length ==0">
					现在还没有新闻哦
				</view>
				<view class="newsContainer" v-else>
					<view class="newsItem" v-for="news in newsDtail" :key="news.title">
						{{news.title}} - {{news.desc}}
					</view>
				</view>
			</view>
		</view>
	</view>

</template>

<script>
	import {
		reactive
	} from 'vue'
	export default {
		setup() {
			let serviceItems = [
				{
					title: "就业咨询",
					imgUrl: "../../static/employment/employment1.png",
				},
				{
					title: "推荐就业",
					imgUrl: "../../static/employment/employment2.png",
				},
				{
					title: "就业产业需求摸排",
					imgUrl: "../../static/employment/employment3.png",
				},
				{
					title: "就业创业",
					imgUrl: "../../static/employment/employment4.png",
				},
			]
			let newsDtail = reactive([])
		return {
			serviceItems,
			newsDtail
		}
		}
	}
</script>

<style lang="scss" scoped>
	.topBar {
		position: relative;
		width: 100vw;
		height: 50px;
		background-color: #e82c29;
		color: #fff;
		line-height: 50px;
		text-align: center;
		font-size: 18px;

		.topIcon {
			position: absolute;
			width: 30px;
			height: 30px;
			z-index: 2;
			left: 10px;
			top: 50%;
			transform: translateY(-50%);
		}
	}

	.banner {
		width: 100%;

		image {
			width: 100%;
			height: 175px;
		}
	}
	.services {
		margin-top: 10px;
		// height: 285px;
		background-color: #fff;
	
		.disc {
			height: 45px;
			text-align: center;
			line-height: 45px;
			border-bottom: 1px solid #f3f3f3;
	
			&::before {
				content: "—";
				margin-right: 5px;
			}
	
			&::after {
				content: "—";
				margin-left: 5px;
			}
		}
	
		.serviceWrap {
			margin-top: 18px;
			display: flex;
			flex-wrap: wrap;
			justify-content: space-between;
	
			.item {
				width: 33.3%;
				height: 100px;
				.imgOuter {
					margin: 0 auto;
					width: 60px;
					height: 60px;
					border-radius: 30px;
					border: 1px solid #e5e5e5;
					display: flex;
					justify-content: center;
					align-items: center;
					image {
						width: 32px;
						height: 32px;
					}
				}
				.serviceTitle {
					margin-top: 5px;
					font-size: 12px;
					text-align: center;
				}
			}
		}
	}
	.news {
		margin-top: 15px;
		background-color: #fff;
		height: 100%;
	
		.newsTitle {
			width: 100%;
			height: 50px;
			display: flex;
			justify-content: space-between;
			align-items: center;
			border-bottom: 1px solid #f3f3f3;
			padding: 0 20px;
			box-sizing: border-box;
			color: #c3c3c6;
			font-size: 14px;
	
			.bold {
				font-weight: 700;
				font-size: 18px;
				color: black;
			}
		}
	
		.newsContent {
			margin-top: 10px;
	
			.emptyNews {
				text-align: center;
			}
		}
	}
</style>

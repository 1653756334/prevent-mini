<template>
	<view class="conbox">
		<view class="topBar">
			<image class="topIcon" src="../../static/home.png"></image>
			<view class="title">
				“遇贫则鸣”防返贫平台
			</view>
		</view>
	</view>
	
</template>

<script>
</script>

<style lang="scss" scoped>
.conbox{
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
	
}
</style>
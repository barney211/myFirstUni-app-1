<template>
	<view class="my-plan-style">
		<!-- 3D轮播 -->
		<view class="">
			<swiper class="imageContainer" @change="handleChange" previous-margin="50upx" next-margin="50upx" circular  autoplay>
				<block v-for="(item,index) in imgList" :key="index">
					<swiper-item class="swiperitem">
						<image class="itemImg" :class="currentIndex == index ? 'swiperactive': ''" :src="item.pic" lazy-load mode="scaleToFill"></image>
					</swiper-item>
				</block>
			</swiper>
		</view>
	</view>
</template>
<script>
	export default {
		data(){
			return {
				currentIndex:0,
				imgList:[
				{pic:require('../static/img/carosoul/panelBg.png')},
				{pic:require('../static/img/carosoul/panelBg.png')},
				{pic:require('../static/img/carosoul/panelBg.png')},
				{pic:require('../static/img/carosoul/panelBg.png')}
				
				]
			}
		},
		methods:{
			handleChange(e){
				var vm=this;
				vm.currentIndex=e.detail.current;
			
			}
		}
	}	
</script>
<style lang="scss">
	// 3D轮播样式
	.imageContainer {
		width: 100%;
		/* height: 500rpx; */
		/* background: #000; */
		height: 325upx;
		background-color: #fff;
	}
	
	.swiperitem {
		/* height: 500rpx; */
		height: 255upx;
		padding: 0upx 0upx;
		box-sizing: border-box;
		position: relative;
		.swiperText {
			display: flex;
			flex-direction: column;
			align-items: center;
			position: absolute;
			top: 56upx;
			left: 51upx;
			z-index: 998;
			width:162upx;
			height:163upx;
			background:rgba(255,255,255,1);
			border-radius:8upx;
			padding:10upx;
			.name {
				font-size:26upx;
				font-weight:500;
				color:rgba(253,57,91,1);
				line-height:37upx;
				margin-bottom: 10upx;
			}
			.zq,.cz {
				font-size:20upx;
				color:rgba(253,57,91,1);
				line-height:35upx;
			}
			.addNl {
				width:120upx;
				height:26upx;
				background:rgba(253,57,91,1);
				border-radius:13upx;
				font-size:20upx;
				font-weight:500;
				color:rgba(255,255,255,1);
				text-align: center;
				line-height: 26upx;
				margin-top: 10upx;
			}
			
		}
	}
	
	.itemImg {
		position: absolute;
		width: 96%;
		/* height: 380rpx; */
		height: 255upx;
		border-radius: 15rpx;
		z-index: 5;
		opacity: 0.7;
		top: 5%;
		left:2%;
		box-shadow:0px 4upx 15upx 0px rgba(153,153,153,0.24);
	}
	
	.swiperactive {
		width: 96%;
		opacity: 1;
		z-index: 10;
		/* height: 430rpx; */
		height: 287upx;
		top: 0%;
		left:2%;
		transition: all .2s ease-in 0s;
	}
	
	.zhankai{
		text-align: center;
		.iconfont{
			margin-left: 10upx;
		}
	}
</style>
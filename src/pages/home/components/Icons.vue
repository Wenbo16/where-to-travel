<template>
  <div class="icons">
  	<swiper>
  		<swiper-slide v-for="(page, index) of pages" :key="index">
		    <div 
		    	class="icon"
				v-for="item of page"
				:key="item.id"
		    >
		    	<div class="icon-img">
		    		<img class="icon-img-content" :src="item.imgUrl">
		    	</div>
		    	<p class="icon-desc">{{item.desc}}</p>
		    </div>
		</swiper-slide>
	</swiper>
  </div>
</template>

<script>

export default {
	name: 'HomeIcons',
	data () {
	  	return {
	  		iconList: [{
	  			id: '0001',
	  			imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
	  			desc: 'Tickets'
	  		}, {
	  			id: '0002',
	  			imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
	  			desc: 'Things to do'
	  		}, {
	  			id: '0003',
	  			imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png',
	  			desc: 'Hiking'
	  		}, {
	  			id: '0004',
	  			imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
	  			desc: 'One day trip'
	  		}, {
	  			id: '0005',
	  			imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
	  			desc: 'Zoos'
	  		}, {
	  			id: '0006',
	  			imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png',
	  			desc: 'Forbidden City'
	  		}, {
	  			id: '0007',
	  			imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/67/9a1678221b8e0e02.png',
	  			desc: 'Water City'
	  		}, {
	  			id: '0008',
	  			imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ed/cf572be30fc32f02.png',
	  			desc: 'Suggestions'
	  		}, {
	  			id: '0009',
	  			imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ed/cf572be30fc32f02.png',
	  			desc: 'Q+'
	  		}]
	  	}
  	},

  	computed: {
  		pages() {
  			const pages =[]
  			this.iconList.forEach((item, index) => {
  				const page = Math.floor(index / 8)
  				if(!pages[page]) {
  					pages[page] = []
  				}
  				pages[page].push(item)
  			})
  			return pages
  		}
  	}
}

</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	@import '~styles/mixins.styl'
	.icons >>> .swiper-container
		overflow: hidden
		height: 0
		padding-bottom: 50%
	.icon
		position: relative
		overflow: hidden
		float: left
		width: 25%
		height: 0
		padding-bottom: 25%
		.icon-img
			position: absolute
			top: 0
			left: 0
			right: 0
			bottom: .44rem
			box-sizing: border-box
			padding: .1rem
			.icon-img-content
				height: 100%
				display: block
				margin: 0 auto
		.icon-desc
			position: absolute
			left: 0
			right: 0
			bottom: 0
			height: .44rem
			line-height: .44rem
			color: $darkTextColor
			text-align: center
			ellipsis()
</style>
<template>
	<view>
		<view class="title">
			{{detail.title}}
		</view>
		<view class="content">
			<rich-text :nodes="detail.content"></rich-text>  
			<!-- rich-text 是富文本，nodes	Array / String	[]	节点列表 / HTML String-->
		</view>
	</view>
</template>
<script>
	export default {
		data() {
			return {
				detail: {},
				id: '',
			}
		},
		async onLoad(options) {  //监听页面加载，其参数为上个页面传递的数据，参数类型为 Object（用于页面传参）
			this.id = options.id;
			let res = await this.$api.info('news', options.id)
			this.detail = res.data;
			this.detail.content = this.detail.content.replace(/<img/g,'<img style="width: 100%;"');
		}
	}
</script>

<style scoped>
	page {
		background: #FFFFFF;
	}

	.title {
		text-align: center;
		font-size: 40upx;
		font-weight: bold;
		margin: 20upx;
	}

	.content {
		margin: 40upx;
		font-size: 30upx;
		line-height: 50upx;
		letter-spacing: 5upx;
	}
</style>

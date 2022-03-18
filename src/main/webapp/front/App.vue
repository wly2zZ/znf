<script>
	export default {
		onLaunch: function() {
			console.log('App初始化')
		},
		onShow: function() {
			console.log('页面加载')
		},
		onHide: function() {
			console.log('App隐藏')
		}
	}
</script>

<style lang="scss">
	@import "/colorui/main.css";
	@import "/colorui/icon.css";
	/*每个页面公共css */
 	@import "/assets/css/style.scss";
	
	.uni-product-list {
		display: flex;
		width: 100%;
		flex-wrap: wrap;
		flex-direction: row;
		margin-top: 60px;
	}
</style>

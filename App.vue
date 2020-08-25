<script>
export default {
	onLaunch: function() {
		console.log('App Launch');
	},
	onShow: function() {
		console.log('App Show');
	},
	onHide: function() {
		console.log('App Hide');
	}
};
</script>

<style>
/* #ifndef APP-PLUS-NVUE */
/* uni.css - 通用组件、模板样式库，可以当作一套ui库应用 */
@import './common/uni.css';

/* 以下样式用于 hello uni-app 演示所需 */
page {
  background-color: #F2F2F2;
  height: 100%;
  font-size: 14px;
  line-height: 1.8;
}

</style>

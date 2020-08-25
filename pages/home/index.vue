<template>
  <view class="home-page">
    <!-- 搜索-->
    <navBar></navBar>
    <!-- tag -->
    <view class="recommend-search">
      <text class="text">推荐：</text>
      <view v-for="(item, index) in recommendList" :key="index" class="tag-view">
        <uni-tag :text="item.text" circle size="small" type="error" />
      </view>
    </view>
    <!-- bg -->
    <view class="bg-view"></view>
    <!--卡片-->
    <uni-card title="标题文字" class="cart_1" @click="clickCard">
      <text class="content-box-text">这是一个基础卡片示例，内容比较多，内容样式可自定义，卡片视图常用来显示完整独立的一段信息，比如一篇文章的预览图、作者信息、时间等，此示例带边框阴影。</text>
    </uni-card>
  </view>
</template>

<script>
import navBar from "../common/navBar";
export default {
  data() {
    return {
      // 推荐
      recommendList: [
        {text: '春装'},
        {text: '女装'},
        {text: '男装'},
        {text: '母婴'},
        {text: '美食'},
        {text: '包包'},
        {text: '美容美妆'}
      ],
      // 轮播
    };
  },
  components: {navBar},
  methods: {
    /**
    * 卡片
    * */
    clickCard() {
      uni.showToast({
        title: '点击卡片',
        icon: 'none'
      })
    },
  }
};
</script>

<style lang="scss" scoped>
.home-page{
  .recommend-search{
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    flex-wrap: wrap;
    background-color: #F75E30;
    padding: 10px;
    .text{
      height:24px;
      line-height: 24px;
      font-size:13px;
      font-weight:400;
      color: #FFF;
    }
    .tag-view {
      margin: 2px 5px 5px;
      line-height: 16px;
    }
  }
  .bg-view{
    background-color: #F75E30;
    height: 180px;
    border-bottom-left-radius: 100px;
    border-bottom-right-radius: 100px;
  }
  .cart_1{
    background-color: #FFFFFF;
  }
}
</style>
<style lang="scss">
.home-page{
  .recommend-search{
    .uni-tag--small {
      line-height: 16px;
    }
  }
}
</style>

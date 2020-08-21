<template>
  <view class="home-page">
    <!-- 搜索-->
    <uni-nav-bar class="search" :fixed="true" background-color="#F75E30" @click-left="handleNavLeft" @click-right="handleNavRight">
      <block slot="left">
        <uni-icons type="scan" color="#FFF"  size="22" style="margin-left: 5px;"/>
      </block>
      <view class="input-view">
        <uni-icons class="uni-icon" type="search" color="#7F7F7F" size="20" />
        <input confirm-type="search" class="input" type="text" value="新一代V3.0智能手环发售" placeholder="输入搜索关键词" @confirm="handleNavSearch"/>
      </view>
      <block slot="right">
        <uni-icons type="shop" color="#FFF"  size="22" style="margin-right: 8px;"/>
        <uni-icons type="chatbubble" color="#FFF"  size="22" />
      </block>
    </uni-nav-bar>
    <view class="recommend-search">
      <text class="text">推荐：</text>
      <view v-for="(item, index) in recommendList" :key="index" class="tag-view">
        <uni-tag :text="item.text" circle size="small" type="error" />
      </view>
    </view>
    <!--轮播区-->
    <view class="bg-view"></view>
    <view class="carousel-view">
      <view class="carousel-content">
        <view>
          <uni-swiper-dot :info="info" :current="current" :dots-styles="dotsStyles" field="content">
            <swiper class="swiper-box" @change="change">
              <swiper-item v-for="(item, index) in info" :key="index">
                <view :class="item.colorClass" class="swiper-item">
                  <image class="image" :src="item.url" mode="aspectFill" />
                </view>
              </swiper-item>
            </swiper>
          </uni-swiper-dot>
        </view>
      </view>
    </view>



  </view>
</template>

<script>
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
      info: [
        {
          colorClass: 'uni-bg-red',
          url: 'https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/shuijiao.jpg',
          content: '内容 A'
        },
        {
          colorClass: 'uni-bg-green',
          url: 'https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/muwu.jpg',
          content: '内容 B'
        },
        {
          colorClass: 'uni-bg-blue',
          url: 'https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/cbd.jpg',
          content: '内容 C'
        }
      ],
      current: 0,
      dotsStyles: {
        backgroundColor: 'rgba(0, 0, 0, .4)',
        border: '1px rgba(0, 0, 0, .3) solid',
        color: '#FFFFFF',
        selectedBackgroundColor: '#FF4A68',
        selectedBorder: '1px rgba(0, 0, 0, .9) solid'
      }
    };
  },
  methods: {
    /**
     * nav left点击
    * */
    handleNavLeft() {
      uni.showToast({
        title: '选择城市'
      });
    },
    /**
     * nav right点击
     * */
    handleNavRight() {
      uni.showToast({
        title: '扫码'
      });
    },
    /**
     * nav 搜索
     * */
    handleNavSearch() {
      uni.showToast({
        title: '搜索'
      });
    },
    /**
    * 轮播切换
    * */
    change(e) {
      this.current = e.detail.current
    },
  }
};
</script>

<style lang="scss" scoped>
.home-page{
  .search{
    .input-view {
      display: flex;
      flex-direction: row;
      flex: 1;
      background-color: #f8f8f8;
      height: 30px;
      border-radius: 15px;
      padding: 0 15px;
      flex-wrap: nowrap;
      margin: 7px 0;
      line-height: 30px;
    }
    .input {
      height: 30px;
      line-height: 30px;
      padding: 0 5px;
      background-color: #f8f8f8;
    }
  }
  .recommend-search{
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    flex-wrap: wrap;
    background-color: #F75E30;
    padding: 20rpx;
    .text{
      height:23px;
      font-size:12pt;
      font-weight:400;
      color: #FFF;
    }
    .tag-view {
      margin: 4rpx 10rpx 10rpx;
      line-height: 16px;
    }
  }
  .bg-view{
    background-color: #F75E30;
    height: 90pt;
    border-bottom-left-radius: 50pt;
    border-bottom-right-radius: 50pt;
  }
  .carousel-view{
    padding: 0 5pt;
    .carousel-content{
      height: 194pt;
      background-color: #FFF;
      border-radius: 10pt 10pt 0 0;
      .swiper-box{
        height: 100pt;
        .swiper-item {
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;
          background-color: #999;
          color: #fff;
          .image {
            img{
              width: 750rpx;
              border-radius: 10pt;
            }
          }
        }
      }
    }
  }
}
</style>
<style lang="scss">
.home-page{
  .search{
    /deep/ .uni-navbar__content{
      width: 100%;
      border-bottom: none;
    }
    /deep/ .uni-navbar__header-btns-left {
      width: 40px;
    }
  }
  .recommend-search{
    .uni-tag--small {
      line-height: 16px;
    }
  }
}
</style>

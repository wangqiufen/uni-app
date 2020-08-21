<template>
  <view class="home-page">
    <!-- 搜索-->
    <uni-nav-bar class="search" :fixed="true" color="#FFF" background-color="#F75E30" left-icon="scan" @click-left="showCity" @click-right="scan">
      <block slot="left">
        <view class="scan-view">
          <uni-icons type="arrowdown" color="#FFF" size="22" />
          <view>扫一扫</view>
        </view>
      </block>
      <view class="input-view">
        <uni-icons class="uni-icon" type="search" color="#7F7F7F" size="15" />
        <input confirm-type="search" class="input" type="text" value="新一代V3.0智能手环发售" placeholder="输入搜索关键词" @confirm="confirm"/>
      </view>
      <block slot="right">
        <view class="scan">
          <view>扫一扫</view>
          <uni-icons type="arrowdown" color="#FFF" size="22" />
        </view>
      </block>
    </uni-nav-bar>





    <!--<view class="recommend-search">
      <text>推荐：</text>
      <uni-badge v-for="(item, index) in recommendList" :key="index" :text="item.text" type="error"></uni-badge>
    </view>
    <swiper indicator-dots="true">
      <swiper-item v-for="(img, key) in imgUrls" :key="key"><image :src="img" /></swiper-item>
    </swiper>
    <view class="uni-padding-wrap uni-common-mt">
      <view class="uni-title">
        <view>本示例为导航栏带搜索框完整功能演示，主要演示有：</view>
        <view>1. 导航栏为 transparent 模式，向上滑动页面，导航栏会从透明变为实色。</view>
        <view>2. 点击搜索框跳转到搜索页面。</view>
        <view>3. 点击导航栏右侧按钮实现关联操作。</view>
        <view>4. 搜索页面为提示词搜索，输入内容实时显示关联词。</view>
        <view>5. 搜索结果根据搜索内容高亮显示文字。</view>
        <view>6. 点击搜索列表或者软键盘搜索按钮，会将结果保存到搜索历史列表。</view>
        <view>7. 点击删除图标，清空历史搜索列表。</view>
        <view>Tips </view>
        <view>1. 本示例目前仅支持 App 端</view>
        <view>2. 所有示例均为演示使用，具体逻辑需要自己实现。</view>

      </view>
    </view>
    <view style="height: 1000upx;"></view>-->
  </view>
</template>

<script>
// import uniIcons from "@/components/uni-icons/uni-icons.vue"
// import uniNavBar from "@/components/uni-nav-bar/uni-nav-bar.vue"
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
      showSwiper: false,
      imgUrls: [
        'https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/muwu.jpg',
        'https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/cbd.jpg'
      ]
    };
  },
  // components: {uniIcons},
  /**
   * 当 searchInput 配置 disabled 为 true 时触发
   */
  onNavigationBarSearchInputClicked(e) {
    console.log('事件执行了')
    uni.navigateTo({
      url: '/pages/template/nav-search-input/detail/detail'
    });
  },
  /**
   *  点击导航栏 buttons 时触发
   */
  onNavigationBarButtonTap() {
    uni.showModal({
      title: '提示',
      content: '用户点击了功能按钮，这里仅做展示。',
      success: res => {
        if (res.confirm) {
          console.log('用户点击了确定');
        }
      }
    });
  },
  methods: {
    showCity() {
      uni.showToast({
        title: '选择城市'
      });
    },
    scan() {
      uni.showToast({
        title: '扫码'
      });
    },
    confirm() {
      uni.showToast({
        title: '搜索'
      });
    }
  }
};
</script>

<style lang="less">
.search{
  .scan-view{
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    width: 100%;
    margin-left: 8px;
    white-space: nowrap;
  }
  .input-view {
    width: 92%;
    display: flex;
    background-color: #FFF;
    height: 30px;
    border-radius: 15px;
    padding: 0 4%;
    flex-wrap: nowrap;
    margin: 7px 0;
    line-height: 30px;
    color: #7E7E7E;
    .uni-icon {
      width: 20px;
      line-height: 30px !important;
    }
    .input {
      height: 30px;
      line-height: 30px;
      width: 94%;
      padding: 0 3%;
    }
  }
}
</style>

<template>
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
    }
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
    }
  }
};
</script>

<style lang="scss" scoped>
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
</style>
<style lang="scss">
.search{
  /deep/ .uni-navbar__content{
    width: 100%;
    border-bottom: none;
  }
  /deep/ .uni-navbar__header-btns-left {
    width: 40px;
  }
}
</style>

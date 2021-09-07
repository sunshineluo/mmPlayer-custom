<template>
  <!--选项-->
  <div class="music-btn">
    <router-link to="/music/playlist" tag="span"><i class="fad fa-list-music"></i>&nbsp;正在播放</router-link>
    <span class="show-960" @click="$emit('onClickLyric')"><i class="fad fa-turntable"></i>&nbsp;打开歌词</span>
    <router-link to="/music/toplist" tag="span"><i class="fad fa-telescope"></i>&nbsp;发现音乐</router-link>
    <router-link to="/music/search" tag="span"><i class="fad fa-search"></i>&nbsp;搜索音乐</router-link>
    <router-link to="/music/userlist" tag="span"><i class="fad fa-user"></i>&nbsp;我的歌单</router-link>
    <router-link to="/music/historylist" tag="span"><i class="fad fa-history"></i>&nbsp;我听过的</router-link>
  </div>
</template>

<script>
export default {}
</script>

<style lang="less" scoped>
.music-btn {
  width: 100%;
  height: 60px;
  font-size: 0;
  white-space: nowrap;
  overflow-x: auto;
  -webkit-overflow-scrolling: touch;
  span {
    display: inline-block;
    height: 40px;
    box-sizing: border-box;
    margin-right: 8px;
    padding: 0 23px;
    border: 1px solid @btn_color;
    color: @btn_color;
    border-radius: 2px;
    font-size: 14px;
    line-height: 40px;
    overflow: hidden;
    cursor: pointer;
    &:nth-last-of-type(1) {
      margin: 0;
    }
    &:hover,
    &.active {
      border-color: @btn_color_active;
      color: @btn_color_active;
    }
  }
  @media (min-width: 960px) {
    span.show-960 {
      display: none;
    }
  }
  @media (max-width: 960px) {
    span.show-960 {
      display: inline-block;
    }
  }/*
  @media (max-width: 768px) {
    height: 50px;
    span {
      height: 35px;
      padding: 0 10px;
      margin-right: 6px;
      line-height: 35px;
    }
  }*/
}
</style>

<template>
  <!--加载动画-->
  <div
    v-show="value"
    class="mm-loading"
    :style="{ backgroundColor: loadingBgColor }"
  >
    <div class="mm-loading-content">
      <span class="loader"></span>
    </div>
    <div class="mm-loading-text">
      <span class="loading-text">加载中</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MmLoading',
  props: {
    // 是否显示
    value: {
      type: Boolean,
      default: true
    },
    // 加载动画背景颜色
    loadingBgColor: {
      type: String,
      default: ''
    }
  }
}
</script>

<style lang="less">
.mm-loading {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 1996;
  background: @load_bg_color;
  /* 自定义添加 */
  backdrop-filter: blur(10px);
  width: 240px; //36%;
  height: 30%;
  margin: auto auto;
  border-radius: 12px;
  display: flex;
  justify-content: center;
  animation: fade-in 0.6s;
  -webkit-animation: fade-in 0.6s;
  .mm-loading-content {
    position: absolute;
    top: 40%;
    width: 100%;
    transform: translateY(-50%);
    text-align: center;
    .circular {
      height: 50px;
      width: 50px;
      animation: loading-rotate 2s linear infinite;
      .path {
        animation: loading-dash 1.5s ease-in-out infinite;
        stroke-dasharray: 90, 150;
        stroke-dashoffset: 0;
        stroke-width: 2;
        stroke: @text_color;
        stroke-linecap: round;
      }
    }
  }
}

//添加加载文字
.mm-loading-text {
    position: absolute;
    bottom: 16%;
}

.loading-text {
    font-size: 1rem;
}

//动画函数
.loader {
  width: 8px;
  height: 40px;
  border-radius: 4px;
  display: block;
  margin: 20px auto;
  position: relative;
  background: currentColor;
  color: #fff;
  box-sizing: border-box;
  animation: animloader 0.3s 0.3s linear infinite alternate;
}

.loader::after,
.loader::before {
  content: '';
  width: 8px;
  height: 40px;
  border-radius: 4px;
  background: currentColor;
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  left: 20px;
  box-sizing: border-box;
  animation: animloader 0.3s 0.45s linear infinite alternate;
}
.loader::before {
  left: -20px;
  animation-delay: 0s;
}

@keyframes animloader {
  0% {
    height: 48px;
  }
  100% {
    height: 4px;
  }
}
</style>

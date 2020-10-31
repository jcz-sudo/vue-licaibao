<template>
  <div id="app">
    <router-view />
  </div>
</template>

<script>
export default {
  methods: {
    // 判断设备是移动端还是PC端
    device() {
      if (
        !navigator.userAgent.match(
          /(iPhone|iPod|Android|ios|iOS|iPad|Backerry|WebOS|Symbian|Windows Phone|Phone)/i
        )
      )
        this.$alert(
          <div style="text-align:center; font-size:20px">
            <h1 style="margin-bottom:10px">
              使用谷歌浏览器手机端浏览效果更佳
            </h1>
          </div>,
          "提示",
          {
            dangerouslyUseHTMLString: true,
          }
        );
    },
  },
  mounted() {
    this.device();
  },
};
</script>

<style lang="scss">
// element-ui的弹出输入框的样式修改
.el-message-box {
  width: 90vw !important;
}
</style>

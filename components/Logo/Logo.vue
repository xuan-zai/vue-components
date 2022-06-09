<template>
  <div class="logo-container">
    <div class="logo" :class="type">
      <img :src="url" />
    </div>
    <div class="logo-title" :class="type">{{ title }}</div>
  </div>
</template>

<script>
export default {
  props: {
    // 图片是否需要填满整个容器
    type: {
      type: String,
      default: "fill",
    },
    // 图片的链接地址
    url: {
      type: String,
      required: true,
    },
    title: {
      type: String,
    },
  },
};
</script>


<style lang="scss" scoped>
.logo-container {
  width: inherit;
  height: 60px;
  border: 1px solid;
  display: flex;
  align-items: center;
  box-sizing: border-box;
  padding: 0 9px;
  font-size: 14px;
  overflow: hidden;
  .logo {
    &.fill {
      width: 100%;
      height: 100%;
    }
    &.nofill {
      width: 45px;
      height: 45px;
      min-width: 45px;
    }
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
  .logo-title {
    &.fill {
      display: none;
    }
    margin-left: 12px;
    font-weight: bold;
  }
}
</style>
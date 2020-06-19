<template>
  <div class="container">
    <h1>📩</h1>
    <h1>Subscribe</h1>
    <p>如何订阅我的文章？</p>

    <hr id="top-hr" />
    <div class="article">
      <p>Big brother drink Coca Cola 🍻</p>

      <h2>如何订阅我的博客？</h2>
      <p>
        我的博客目前使用 Hexo 搭建与编译，部署于 Tencent CloudBase。我提供了 RSS
        订阅链接，可以直接订阅我的个人博客啦~
      </p>
      <AppCard
        msg="博客"
        stars="⭐⭐⭐⭐⭐"
        description="利用 RSS 订阅我的博客更新"
        icon="bulb.png"
        link1Tooltip="我的博客地址"
        link2Tooltip="我的博客 RSS 订阅链接"
        link1="https://royce2003.top/"
        link2="https://royce2003.top/atom.xml"
        rightIcon1="bookmark.png"
        rightIcon2="rss-blue.png"
      />

      <h2>最后，感谢。</h2>
      <p>感谢大哥的关注！您的支持是我更新的最大动力。ღ( ´･ᴗ･` )比心</p>
    </div>
  </div>
</template>

<script>
import AppCard from '@/components/AppCard.vue'

export default {
  name: 'subscribe',
  components: {
    AppCard,
  },
}
</script>

<style lang="css" scoped>
h2 {
  font-weight: 700;
  font-size: 20px;
  padding: 10px 0;
}

h3 {
  font-weight: 700;
  font-size: 18px;
  padding: 18px 0 0 0;
  margin: 0;
}

ul {
  padding-left: 15px;
  line-height: 30px;
  margin: 0;
}

p {
  line-height: 30px;
}
</style>

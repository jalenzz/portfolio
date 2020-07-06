<template>
  <div class="container">
    <h1>📩</h1>
    <h1>Subscribe</h1>

    <hr id="top-hr" />
    <div class="article">

      <h2>How to subscribe to my blog?</h2>
      <p>
        My blog is powerd by Hexo and deployed on Tencent CloudBase. I have provided a link to RSS feeds.
      </p>
      <AppCard
        msg="Blog"
        stars="⭐⭐⭐⭐⭐"
        description="Subscribe my blog by RSS"
        icon="bulb.svg"
        link1Tooltip="Link of my blog"
        link2Tooltip="Link of the RSS"
        link1="https://blog.JalenChuh.cn"
        link2="https://blog.JalenChuh.cn/atom.xml"
        rightIcon1="bookmark.svg"
        rightIcon2="rss-blue.svg"
      />

      <h2>End</h2>
      <p>Thank you for your follow! Your support is my biggest motivation to update.</p>
      <p>Big brother drink Coca Cola. 🍻</p>

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

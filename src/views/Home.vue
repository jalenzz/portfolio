<template>
  <div class="container">
    <img id="avatar" alt="avatar" src="https://rmt.dogedoge.com/fetch/royce/storage/royce.png?fmt=webp" />
    <h1>Royce</h1>
    <h2>👨‍🎨 👨‍💻</h2>

    <p>Student /  OIer</p>

    <hr id="top-hr" />
    <h3>🎉 Where to find me:</h3>
    <div id="card-container">
      <Card
        msg="博客 Blog"
        backgroundColor="#ff8a0f"
        description="📘 主站，啥都写"
        textColor="#FFFFFF"
        icon="tcb.png"
        link="https://royce2003.top"
      />
      <Card
        msg="更简约的博客"
        backgroundColor="#ca2c2a"
        description="📒 文章不一定和主站同步"
        textColor="#FFFFFF"
        icon="tcb.png"
        link="https://blog.royce2003.top"
      />
      <Card
        msg="GitHub"
        backgroundColor="#24292E"
        description="📦 我的一些仓库"
        textColor="#FFFFFF"
        icon="github.png"
        link="https://github.com/royce003"
      />
    </div>
  </div>
</template>

<script>
import Card from '@/components/Card.vue'

export default {
  components: {
    Card,
  },
}
</script>

<style lang="css" scoped>
#copyright:hover {
  border: none;
}
</style>

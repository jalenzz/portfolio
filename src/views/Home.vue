<template>
  <div class="container">
    <img id="avatar" alt="avatar" src="https://rmt.dogedoge.com/fetch/royce/storage/avatar.png?fmt=webp" />
    <h1>Jalen Chuh</h1>
    <p>Student / Developer / Writer</p>

    <hr id="top-hr" />
    <h3>🔍 Where to find me:</h3>
    <div id="card-container">
      <Card
        msg="Blog"
        backgroundColor="#ff8a0f"
        description="📘 My blog"
        textColor="#FFFFFF"
        icon="tcb.svg"
        link="https://blog.JalenChuh.cn"
      />
      <Card
        msg="SSPAI"
        backgroundColor="#DA282A"
        description="✏️ I'm writing here"
        textColor="#FFFFFF"
        icon="sspai.svg"
        link="https://sspai.com/u/Jalen/posts"
      />
      <Card
        msg="GitHub"
        backgroundColor="#24292E"
        description="📦 Some repositories"
        textColor="#FFFFFF"
        icon="github.svg"
        link="https://github.com/JalenChuh"
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

#card-container a:hover {
  text-decoration: none;
}
</style>

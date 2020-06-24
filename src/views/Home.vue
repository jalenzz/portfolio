<template>
  <div class="container">
    <img id="avatar" alt="avatar" src="https://rmt.dogedoge.com/fetch/royce/storage/royce.png?fmt=webp" />
    <h1>Royce</h1>
    <h2>👨‍🎨 👨‍💻</h2>

    <p>Student /  OIer</p>

    <hr id="top-hr" />
    <h3>🔍 Where to find me:</h3>
    <div id="card-container">
      <Card
        msg="Blog"
        backgroundColor="#ca2c2a"
        description="📘 My personal blog"
        textColor="#FFFFFF"
        icon="tcb.png"
        link="https://royce2003.top"
      />
      <!-- <Card
        msg="Blog2"
        backgroundColor="#ca2c2a"
        description="📒 without decoration"
        textColor="#FFFFFF"
        icon="tcb.png"
        link="https://blog.royce2003.top"
      /> -->
      <Card
        msg="GitHub"
        backgroundColor="#24292E"
        description="📦 My repositories"
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

#card-container a:hover {
  text-decoration: none;
}
</style>

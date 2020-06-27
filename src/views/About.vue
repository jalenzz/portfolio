<template>
  <div class="container">
    <h1>👓</h1>
    <h1>About</h1>
    <!-- <p>这人是谁啊，这么牛逼哄哄的？</p> -->

    <hr id="top-hr" />
    <div class="article">
      <h2>About Me</h2>
        <ul>
        <li>Hi, I'm JalenChuh(Royce), a student in an unknow high school. Freshmen.</li>
        <li>My favorite</li>
          <ul>
            <li>Sport: 🏓</li>
            <li>Color: #FF779A</li>
            <li>OS: iOS(never used MacOS😭)</li>
            <li>{ } Line break: Yes! 🍻</li>
            <li>Editor: VS Code</li>
            <li>Emoji: Microsoft</li>
            <li>Serif font: Noto Serif SC, Roboto Slab</li>
            <li>Monospaced font: Cascadia Code, Fira Code</li>
            <li>
              Tab:
                <ul>
                  <li>2 space in coding</li>
                  <li>4 space in OI</li>
                </ul>
            </li>
          </ul>
        </ul>
        <p>Thanks for coming. 🙇</p>

      <h2>My Project</h2>
      <p>
        Almost all projects(now, only one) I have done are open source on
        <a href="https://github.com/royce003" target="_blank">GitHub</a>
        , weclcome star and follow.
      </p>

      <GitHubCard
        title="🔥 Tank War"
        link="https://github.com/royce003/tankwar"
        :info="tankwarinfo"
        :loading="loading"
      >
        <p>
          A tank war writted by Kotlin. Yes, it's that you palyed in 4399 when you are a kid.<br>
          base on: <a href="https://github.com/xiaoqisz/kotlinGameEngine" target="_blank">kotlinGameEngine:v0.0.4</a>
        </p>
      </GitHubCard>

      <h2>My Devices</h2>
      <ul>
        <li>
          HONOR MagicBook Pro
          <ul>
            <li>CPU: AMD Ryzen 5 3550H</li>
            <li>RAM: 8GB (4GB×2) DDR4 2400MHz</li>
            <li>SSD: SAMSUNG MZVLB512HAJQ-00000 512GB</li>
          </ul>
        </li>
        <li>MEIZU 16th</li>
        <li>Redmi Note 3</li>
        <li>iPad Air 2</li>
      </ul>

      <h2>Contact</h2>
      <ul>
        <li>📍 Fujian, China</li>
        <li>📫 Email: JalenChuh[AT]gmail.com</li>
        <li>📝 leave messages: <a href="https://royce2003.top/messageboard/" target="_blank">message board</a></li>
      </ul>
    <p>
      至于为什么全站英文呢？<br>
      闲着无聊😜而且我这翻译都看得懂🤣<br>
      就这就这？就这！<br>
      <b>🚨 求助，大括号换行应该怎么翻译！</b>
    </p>
    </div>
  </div>
</template>

<script>
import GitHubCard from '@/components/GitHubCard.vue'

export default {
  components: {
    GitHubCard,
  },
  data() {
    return {
      loading: true,
      dowwwInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
      substatsInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
      fatesInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
      sspaiCardInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
      dotfilesInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
    }
  },
  mounted() {
    const githubApiUrl = 'https://api.github.com/repos'

    const tankwarAxios = this.axios.get(`${githubApiUrl}/royce003/tankwar`)

    this.axios
      .all([tankwarAxios])
      .then(
        this.axios.spread((...resp) => {
          this.loading = false
          this.tankwarinfo = resp[0].data
        }),
      )
      .catch(err => {
        this.loading = false
        // eslint-disable-next-line no-console
        console.error(err)
      })
  },
}
</script>

<style lang="css" scoped>
h2 {
  font-weight: 700;
  font-size: 20px;
  padding: 10px 0;
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

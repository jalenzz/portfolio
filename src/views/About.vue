<template>
  <div class="container">
    <h1>👓</h1>
    <h1>About</h1>
    <!-- <p>这人是谁啊，这么牛逼哄哄的？</p> -->

    <hr id="top-hr" />
    <div class="article">
      <h2>About Me</h2>
        <ul>
        <li>Hi, I'm JalenChuh, a student in an unknow high school. Freshmen.</li>
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
        Almost all projects I have done are open source on
        <a href="https://github.com/JalenChuh" target="_blank">GitHub</a>
        , weclcome star and follow.
      </p>
      <GitHubCard
        title="🔥 Tank War"
        link="https://github.com/JalenChuh/tankwar"
        :info="tankwarInfo"
        :loading="loading"
      >
        <p>
          A tank war writted by Kotlin. Yes, it's that you palyed in 4399 when you are a kid.<br>
          base on: <a href="https://github.com/xiaoqisz/kotlinGameEngine" target="_blank">kotlinGameEngine:v0.0.4</a>
        </p>
      </GitHubCard>
      <GitHubCard
        title="💄 Portfolio"
        link="https://github.com/JalenChuh/homepage"
        :info="portfolioInfo"
        :loading="loading"
      >
        <p>
          My home page. Design by: <a href="https://spencerwoo.com/" target="_blank">@SpencerWoo</a>
        </p>
      </GitHubCard>
      <GitHubCard
        title="🍻 Blog"
        link="https://blog.JalenChuh.cn"
        :info="blogInfo"
        :loading="loading"
      >
        <p>
          My blog. Powered by Hexo. Theme - Cards
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
        <li>📝 leave messages: <a href="https://blog.JalenChuh.cn/about/" target="_blank">Guestbook</a></li>
      </ul>
    <!-- <p>
      至于为什么全站英文呢？<br>
      闲着无聊😜而且我这翻译都看得懂🤣<br>
      就这就这？就这！<br>
      <b>🚨 求助，大括号换行应该怎么翻译！</b>
    </p> -->
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
      tankwarInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
      portfolioInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
      blogInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
    }
  },
  mounted() {
    const githubApiUrl = 'https://api.github.com/repos'

    const tankwarAxios = this.axios.get(`${githubApiUrl}/JalenChuh/tankwar`)
    const portfolioAxios = this.axios.get(`${githubApiUrl}/JalenChuh/homepage`)
    const blogAxios = this.axios.get(`${githubApiUrl}/JalenChuh/blog`)

    this.axios
      .all([tankwarAxios, portfolioAxios, blogAxios])
      .then(
        this.axios.spread((...resp) => {
          this.loading = false
          this.tankwarInfo = resp[0].data
          this.portfolioInfo = resp[1].data
          this.blogInfo = resp[2].data
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

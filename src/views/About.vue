<template>
  <div class="container">
    <h1>🍮</h1>
    <h1>About</h1>

    <hr id="top-hr" />
    <div class="article">
      <h2>About Me</h2>
        <ul>
        <li>Hi, I'm JalenChuh, a high school student. Sophomore.</li>
        <li>My favorite</li>
          <ul>
            <li>Sport: 🏓</li>
            <li >Color: <span style="color: #FF7790">#FF7790</span></li>
            <li>OS: iOS</li>
            <li>{ } Line break: No! 🍻</li>
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
        title="🚀 baidu-url-submit-by-using-sitemap"
        link="https://github.com/JalenChuh/baidu-url-submit-by-using-sitemap"
        :info="submitInfo"
        :loading="loading"
      >
        <p>
          Automatically extract the links in the sitemap and use Baidu API to push them to <em>ziyuan.baidu.com</em>.

        </p>
      </GitHubCard>
      <GitHubCard
        title="🍻 Blog"
        link="https://github.com/JalenChuh/blog"
        :info="blogInfo"
        :loading="loading"
      >
        <p>
          My blog. Powered by Gridsome. Theme - gridsome-starter-blog.
        </p>
      </GitHubCard>

      <h2>Contact</h2>
      <ul>
        <li>📍 Fujian, China</li>
        <li>📫 Email: <a href="javascript:location='mailto:\u006a\u0061\u006c\u0065\u006e\u0063\u0068\u0075\u0068\u0040\u0067\u006d\u0061\u0069\u006c\u002e\u0063\u006f\u006d';void 0">jalenchuh[AT]gmail.com</a></li>
        <li>📝 Guestbook: <a href="https://blog.jalenchuh.cn/about">Guestbook</a></li>
      </ul>
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
      submitInfo: {
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
    const submitAxios = this.axios.get(`${githubApiUrl}/JalenChuh/baidu-url-submit-by-using-sitemap`)
    const blogAxios = this.axios.get(`${githubApiUrl}/JalenChuh/blog`)

    this.axios
      .all([tankwarAxios, submitAxios, blogAxios])
      .then(
        this.axios.spread((...resp) => {
          this.loading = false
          this.tankwarInfo = resp[0].data
          this.submitInfo = resp[1].data
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

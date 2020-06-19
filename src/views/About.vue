<template>
  <div class="container">
    <h1>👓</h1>
    <h1>About</h1>
    <p>这人是谁啊，这么牛逼哄哄的？</p>

    <hr id="top-hr" />
    <div class="article">
      <p>
        大家好，我是 Royce，正在一所不知名高中读高一，给大家鞠躬了。🙇
      </p>

      <h2>我的项目</h2>
      <p>
        我所做过的项目几乎（就那么一个）都开源于
        <a href="https://github.com/royce003" target="_blank">GitHub</a> 上面，欢迎大家 Star + Fork，笔芯 (✿◡‿◡)
      </p>

      <GitHubCard
        title="🔥 Tank War"
        link="https://github.com/royce003/tankwar"
        :info="tankwarinfo"
        :loading="loading"
      >
        <p>
          Tank War: 一个由 Kotlin 编写的坦克大战。没错，就是小时候经常在 4399 里面玩的那个。（刚学，啥都不会）<br>
          base on: <a href="https://github.com/xiaoqisz/kotlinGameEngine" target="_blank">kotlinGameEngine:v0.0.4</a>
        </p>
      </GitHubCard>

      <h2>我的设备</h2>
      <ul>
        <li>
          荣耀 MagicBook Pro
          <ul>
            <li>
              配置清单：
              <ul>
                <li>CPU: AMD Ryzen 5 3550H</li>
                <li>RAM: 8GB (4GB×2) DDR4 2400MHz</li>
                <li>SSD: SAMSUNG MZVLB512HAJQ-00000 512GB</li>
              </ul>
            </li>
          </ul>
        </li>
        <li>MEIZU 16th</li>
        <li>Redmi Note 3</li>
        <li>iPad Air 2</li>
      </ul>

      <h2>联系我</h2>
      <ul>
        <li>📍 Fujian, China</li>
        <li>📝 留言板: <a href="https://royce2003.top/messageboard/" target="_blank">message board</a></li>
        <li>📫 邮箱: royce2003[AT]qq.com</li>
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

<template>
  <div class="container">
    <h1>📈</h1>
    <h1>Stats</h1>

    <hr id="top-hr" />
    <div class="col-container">
      <div class="row-container">
        <statCard
          statTitle="GitHub"
          :followers="github"
          suffix="followers"
          icon="github.png"
          :loading="loading"
          link="https://github.com/JalenChuh"
        />
        <statCard
          statTitle="SSPAI"
          :followers="sspai"
          suffix="follow"
          icon="sspai.png"
          :loading="loading"
          link="https://sspai.com/u/Jalen/posts"
        />
      </div>
      <div class="row-container">
        <statCard
          statTitle="RSS"
          :followers="rss"
          suffix="subscribers"
          icon="rss.png"
          :loading="loading"
          link="https://blog.jalenchuh.cn/atom.xml"
        />
      </div>
    </div>

    <div id="substats-footer">
      * Follower statistics powered by:
      <a href="https://api.spencerwoo.com/substats">Substats</a>.
    </div>
  </div>
</template>

<script>
import statCard from '@/components/StatCard.vue'

export default {
  components: {
    statCard,
  },
  data() {
    return {
      sspai: 0,
      github: 0,
      rss: 0,
      loading: true,
    }
  },
  mounted() {
    const apiUrl = 'https://api.spencerwoo.com/substats'
    const rssUrl = 'https://blog.jalenchuh.cn/atom.xml'
  
    const githubAxios = this.axios.get(`${apiUrl}/?source=github&queryKey=JalenChuh`)
    const sspaiAxios = this.axios.get(`${apiUrl}/?source=sspai&queryKey=Jalen`)
    const rssAxios = this.axios.get(`${apiUrl}/?source=feedly|inoreader|feedsPub&queryKey=${rssUrl}`)

    this.axios
      .all([
        githubAxios,
        sspaiAxios,
        rssAxios,
      ])
      .then(
        this.axios.spread((...responses) => {
          this.loading = false
          this.github = responses[0].data.data.totalSubs
          this.sspai = responses[1].data.data.totalSubs
          this.rss = responses[2].data.data.totalSubs
        }),
      )
      .catch(errs => {
        this.loading = false
        // eslint-disable-next-line no-console
        console.error(errs)
      })
  },
}
</script>

<style lang="css" scoped>
.col-container {
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  justify-content: flex-start;
  align-items: stretch;
  align-content: center;
}

.row-container {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: stretch;
  align-content: stretch;
}

@media screen and (max-width: 760px) {
  .row-container {
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    justify-content: flex-start;
    align-items: stretch;
    align-content: center;
  }
}

a {
  text-decoration: none;
}

#substats-footer {
  color: #666666;
  text-align: left;
  margin: 60px 0 0 0;
}
</style>

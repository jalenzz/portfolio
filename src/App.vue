<template>
  <div id="app">
    <vue-particles
      class="particles"
      color="#000000"
      :particleOpacity="0.3"
      :particlesNumber="20"
      shapeType="circle"
      :particleSize="4"
      :lineLinked="false"
      :moveSpeed="3"
      :hoverEffect="false"
      :clickEffect="false"
    />

    <vue-navigation-bar :options="navbarOptions">
      <template v-slot:custom-section>
        <div class="link">
          <router-link to="/">HOME</router-link>
        </div>
        <div class="link">
          <router-link to="/subscribe">SUBSCRIBE</router-link>
        </div>
        <div class="link">
          <router-link to="/about">ABOUT</router-link>
        </div>
        <!-- <div class="link">
          <router-link to="/stats">STATS</router-link>
        </div> -->
      </template>
    </vue-navigation-bar>

    <transition name="fade" mode="out-in">
      <router-view />
    </transition>

    <div id="footer">
      <div id="footer-text">
        <center>
          <p id="footer-copyright">©{{ getYear() }} Jalen Chuh | <a style="text-decoration: none;" href="http://beian.miit.gov.cn/" target="_blank">闽ICP备20005437号-1</a></p>
          <a href="https://github.com/spencerwooo/portfolio" target="_blank"><img style="height: 60px" src="/copyright.svg" alt="copyright"/></a>
        </center>
      </div>
    </div>
  </div>
</template>

<script>
import 'vue-navigation-bar/dist/vue-navigation-bar.css'

export default {
  name: 'app',

  data() {
    return {
      navbarOptions: {
        elementId: 'main-navbar',
        mobileBreakpoint: 992,
        ariaLabelMainNav: 'Main Navigation',
        menuOptionsRight: [
          {
            type: 'button',
            text: '🌟 FOLLOW ME ON GITHUB',
            path: 'https://github.com/royce003',
            class: 'button-github',
          },
        ],
      },
    }
  },
  methods: {
    getYear() {
      return new Date().getFullYear()
    },
  },
}
</script>

<style>
@import url('https://fonts.dogedoge.com/css2?family=Roboto+Slab:wght@400;500;700&display=swap');

.particles {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 90%;
  z-index: -9999;
}

* {
  font-family: Roboto Slab, 'Noto Serif SC', serif, -apple-system, BlinkMacSystemFont, Segoe UI, Helvetica,
  Arial, pingfang sc, source han sans sc, noto sans cjk sc, sarasa gothic sc,
  microsoft yahei, sans-serif, Apple Color Emoji, Segoe UI Emoji;
}

html,
body {
  margin: 0;
  padding: 0;
}

.animation-fade-in {
  -webkit-animation: fade-in-bottom 0.4s cubic-bezier(0.39, 0.575, 0.565, 1) both;
  animation: fade-in-bottom 0.4s cubic-bezier(0.39, 0.575, 0.565, 1) both;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #000;
  background-color: #fafafa;
  -webkit-animation: fade-in-bottom 0.4s cubic-bezier(0.39, 0.575, 0.565, 1) both;
  animation: fade-in-bottom 0.4s cubic-bezier(0.39, 0.575, 0.565, 1) both;
}

.container {
  text-align: center;
  margin: 0px auto 0 auto;
  max-width: 664px;
  padding: 0px 20px 40px 20px;
}

#main-navbar {
  padding-left: 15px;
  padding-right: 5px;
  background-color: #fafafa;
}

#main-navbar,
#main-navbar .link a,
#main-navbar .button-github {
  font-weight: 700;
}

#main-navbar .button-github {
  background: #fafafa;
  color: #000;
  border: 1.5px solid #0070F3;
  /* border-radius: 50px; */
  transition: 0.3s;
}

#main-navbar .button-github:hover {
  background: #0070F3;
  color: #ffffff;
  -webkit-box-shadow: 0px 10px 40px -10px #0070F3;
  -moz-box-shadow: 0px 10px 40px -10px #0070F3;
  box-shadow: 0px 10px 40px -10px #0070F3;
}

.vnb__collapse-button img {
  width: 24px;
  height: 24px;
  padding-bottom: 3px;
}

.vnb__menu-options--right {
  margin-left: 0;
  padding-left: 10px;
}

.vnb__popup__top__close-button {
  padding-top: 10px;
}

.link {
  padding: 0px 10px 0 10px;
  cursor: pointer;
  -webkit-transition: color 0.2s ease-in;
  transition: color 0.2s ease-in;
}

.link a {
  text-decoration: none;
  font-weight: 500;
  color: #595959;
  font-size: 1rem;
}

.vnb__popup__bottom__custom-section .link {
  padding-bottom: 10px;
}

#avatar {
  width: 120px;
  height: 120px;
  border-radius: 60px;
  margin-top: 40px;
}

.article {
  text-align: left;
}

h1 {
  font-weight: 700;
  font-size: 28px;
}

h2 {
  font-weight: 400;
  font-size: 20px;
  padding: 20px 0;
}

hr {
  width: 100px;
  margin: 60px 0 0 0;
  border-top: solid 3px #000;
}

p,
ul,
li,
span {
  color: #555555;
}

#top-hr {
  width: 100px;
  margin: 60px auto;
  border-top: solid 3px #0070F3;
}

.social-media-card {
  display: flex;
  align-items: center;
  margin: 20px 0;
}

.social-media-card .media-icon {
  width: 20px;
  height: 20px;
  padding-right: 10px;
}

.container a {
  text-decoration: none;
  color: #0070F3;
}

.container a:hover {
  text-decoration: underline;
}

#others {
  text-align: left;
}

#footer {
  padding: 20px 20px;
  background-color: #000;
}

#footer-text {
  margin: 0px auto;
  max-width: 664px;
  color: #ffffff;
}

#footer-text a,
#busuanzi_value_site_pv,
#footer-copyright {
  color: #ffffff;
}

.fade-enter-active,
.fade-leave-active {
  transition-duration: 0.3s;
  transition-property: opacity;
  transition-timing-function: ease;
}

.fade-enter,
.fade-leave-active {
  opacity: 0;
}
</style>

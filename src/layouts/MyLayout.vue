<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated class="bg-white text-grey-8 q-py-xs">
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          aria-label="Menu"
          icon="menu"
        />

        <q-btn flat no-caps no-wrap class="q-ml-xs" v-if="$q.screen.gt.xs">
          <q-icon name="fas fa-meteor" color="red" size="28px" />
          <q-toolbar-title shrink class="text-weight-bold">
            Web3D 99号空间站
          </q-toolbar-title>
        </q-btn>

        <q-space />

        <div class="YL__toolbar-input-container row no-wrap">
          <q-input dense outlined square v-model="search" placeholder="Search" class="bg-white col" />
          <q-btn class="YL__toolbar-input-btn" color="grey-3" text-color="grey-8" icon="search" unelevated />
        </div>

        <q-space />

        <div class="q-gutter-sm row items-center no-wrap">
          <q-btn round dense flat color="grey-8" icon="video_call" v-if="$q.screen.gt.sm">
            <q-tooltip>Create a video or post</q-tooltip>
          </q-btn>
          <q-btn round dense flat color="grey-8" icon="apps" v-if="$q.screen.gt.sm">
            <q-tooltip>Apps</q-tooltip>
          </q-btn>
          <q-btn round dense flat color="grey-8" icon="message" v-if="$q.screen.gt.sm">
            <q-tooltip>Messages</q-tooltip>
          </q-btn>
          <q-btn round dense flat color="grey-8" icon="notifications">
            <q-badge color="red" text-color="white" floating>
              2
            </q-badge>
            <q-tooltip>Notifications</q-tooltip>
          </q-btn>
          <q-btn round flat>
            <q-avatar size="26px">
              <img src="statics/favicon128.ico">
            </q-avatar>
            <q-tooltip>Account</q-tooltip>
          </q-btn>
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      bordered
      show-if-above
      content-class="bg-grey-2"
      :width="240"
    >
      <q-item-label header class="text-weight-bold text-uppercase">
        首页相关
      </q-item-label>

      <q-scroll-area class="fit">
        <q-list padding>
          <q-item v-for="link in links1" :key="link.text" v-ripple clickable tag="a" target="_blank" :href="link.url">
            <q-item-section avatar>
              <q-icon color="grey" :name="link.icon" />
            </q-item-section>
            <q-item-section>
                <q-item-label>{{ link.text }}</q-item-label>
            </q-item-section>
          </q-item>

          <q-separator class="q-my-md" />

          <q-item-label header class="text-weight-bold text-uppercase">
            webGL教学
          </q-item-label>

          <q-item v-for="link in links2" :key="link.text" v-ripple clickable tag="a" target="_blank" :href="link.url">
            <q-item-section avatar>
              <q-icon color="grey" :name="link.icon" />
            </q-item-section>
            <q-item-section>
              <q-item-label>{{ link.text }}</q-item-label>
            </q-item-section>
          </q-item>

          <q-separator class="q-mt-md q-mb-xs" />

          <q-item-label header class="text-weight-bold text-uppercase">
            webGl工具集
          </q-item-label>

          <q-item v-for="link in links3" :key="link.text" v-ripple clickable tag="a" target="_blank" :href="link.url">
            <q-item-section avatar>
              <q-icon color="grey" :name="link.icon" />
            </q-item-section>
            <q-item-section>
              <q-item-label>{{ link.text }}</q-item-label>
            </q-item-section>
          </q-item>

          <q-separator class="q-my-md" />
          <q-item-label header class="text-weight-bold text-uppercase">
            webGL星路
          </q-item-label>

          <q-item v-for="link in links4" :key="link.text" v-ripple clickable tag="a" target="_blank" :href="link.url">
            <q-item-section avatar>
              <q-icon color="grey" :name="link.icon" />
            </q-item-section>
            <q-item-section>
              <q-item-label>{{ link.text }}</q-item-label>
            </q-item-section>
          </q-item>
<!-- <q-item-label header class="text-weight-bold text-uppercase">
            join US
          </q-item-label>

          <q-item v-for="link in links4" :key="link.text" v-ripple clickable tag="a" target="_blank" :href="link.url">
            <q-item-section avatar>
              <q-icon color="grey" :name="link.icon" />
            </q-item-section>
            <q-item-section>
              <q-item-label>{{ link.text }}</q-item-label>
            </q-item-section>
          </q-item> -->
          <q-separator class="q-mt-md q-mb-lg" />
          <div class="q-px-md text-grey-9">
            <div class="row items-center q-gutter-x-sm q-gutter-y-xs">
              <a
                v-for="button in buttons1"
                :key="button.text"
                class="YL__drawer-footer-link"
                href="javascript:void(0)"
              >
                {{ button.text }}
              </a>
            </div>
          </div>
          <div class="q-py-md q-px-md text-grey-9">
            <div class="row items-center q-gutter-x-sm q-gutter-y-xs">
              <a
                v-for="button in buttons2"
                :key="button.text"
                class="YL__drawer-footer-link"
                href="javascript:void(0)"
              >
                {{ button.text }}
              </a>
            </div>
          </div>
        </q-list>
      </q-scroll-area>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  name: 'MyLayout',
  data () {
    return {
      leftDrawerOpen: false,
      search: '',
      links1: [
        { icon: 'home', text: '首页', url: '/' },
        { icon: 'local_movies', text: '视频秀', url: 'https:www.baidu.com' },
        // { icon: 'whatshot', text: 'Trending', url: 'https:www.baidu.com' },
        { icon: 'apps', text: '介绍', url: 'https:www.baidu.com' }
      ],
      links2: [
        { icon: 'folder', text: '课程介绍', url: 'https:www.baidu.com' },
        { icon: 'live_tv', text: '课程视频', url: 'https:www.baidu.com' },
        { icon: 'fas fa-code', text: '实战报名', url: 'https:www.baidu.com' },
        { icon: 'thumb_up_alt', text: '一对一辅导', url: 'https:www.baidu.com' }
      ],
      links3: [
        { icon: 'settings', text: '工具汇总', url: 'https:www.baidu.com' },
        { icon: 'flag', text: '安装教程', url: 'https:www.baidu.com' },
        { icon: 'help', text: '请求协助', url: 'https:www.baidu.com' },
        { icon: 'feedback', text: '分享社区', url: 'https:www.baidu.com' }
      ],
      links4: [
        { icon: 'fab fa-youtube', text: '时间长河', url: 'https:www.baidu.com' },
        { icon: 'local_movies', text: '磕磕碰碰', url: 'https:www.baidu.com' },
        { icon: 'videogame_asset', text: '槽点满满', url: 'https:www.baidu.com' },
        { icon: 'live_tv', text: '未完待续', url: 'https:www.baidu.com' }
      ],
      buttons1: [
        { text: 'Author:' },
        { text: 'Aemon' },
        { text: 'Scqilin' },
        { text: 'Ethan' }
      ],
      buttons2: [
        { text: 'email:' },
        { text: 'space_station99@126.com' }
      ]
    }
  }
}
</script>

<style lang="stylus">
.YL
  &__toolbar-input-container
    min-width 100px
    width 55%
  &__toolbar-input-btn
    border-radius 0
    border-style solid
    border-width 1px 1px 1px 0
    border-color rgba(0,0,0,.24)
    max-width 60px
    width 100%
  &__drawer-footer-link
    color inherit
    text-decoration none
    font-weight 500
    font-size .75rem
    &:hover
      color #000
</style>

<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />

        <q-toolbar-title>
          Quasar App
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-primary"
    >
      <q-list>
        <q-item-label
          header
          class="text-head-center"
        >
          <img class="profile-image" src="~assets/twitter_icon2.jpg" alt="no img">
        </q-item-label>

           <q-tabs
            v-model="tab"
            vertical
            class="text-info"
            >
          <EssentialLink
            v-for="link in essentialLinks"
            :key="link.title"
            v-bind="link"
            class="text-center"
          />
        </q-tabs>

    </q-list>
  </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksData = [
  {
    title: 'Dashboard',
    link: '#/dashboard'
  },
  {
    title: 'Map',
    link: '#/map'
  },
  {
    title: 'Report',
    link: '#/report'
  },
  {
    title: 'Log out',
    link: '/'
  }
]

export default {
  name: 'MainLayout',
  components: { EssentialLink },
  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData,
      tab: 'mails'
    }
  }
}
</script>

<style lang="scss" scoped>
$center: center;
$bold: bold;
$inset: inset;
$menu-bar-color: lightgray;
  .profile-image{
    border-radius: 50%;
    width:50%;
  }
  .text-center{
    text-align: $center;
    border-bottom-style: $inset;
    border-bottom-width: 1px;
    border-color: $menu-bar-color;
  }
  .text-head-center{
    text-align: $center;
    text-shadow: 2px;
  }
</style>

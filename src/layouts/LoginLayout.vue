<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-toolbar-title>
          Mable
        </q-toolbar-title>

        <div>BY ManaLab PSU</div>
      </q-toolbar>
    </q-header>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  name: 'MainLayout',
  data () {
    return {
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

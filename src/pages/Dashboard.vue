<template>
  <div id="user-card" class="flex-break">
    <TagButton />
    <UserDisplay />
    <UserOffline />
    <UserOffline />
  </div>
</template>

<script>
import TagButton from 'components/TagButton.vue'
import UserDisplay from 'components/Userdisplay.vue'
import UserOffline from 'components/Useroffline.vue'

export default {
  components: { UserDisplay, UserOffline, TagButton },
  data () {
    return {
      name: 'user-card',
      components: {
        UserDisplay,
        UserOffline,
        TagButton
      }
    }
  }
}
</script>

<style lang="sass" scoped>
.my-card
  width: 100%
  max-width: 300px
  margin: 2rem
.flex-break
  display: flex
  padding: 2rem
.card-zone
  background-color: #457b9d
  text-align: center
  height: 100%
  padding: 0rem
.icon-zone
  background-color: green
  border-style: solid
  border-radius: 50%
  border-width: 3px
  color: white
  display: inline-block
  height: 100px
  width: 100px
  margin: 2rem 0rem
.card-zone-offine
  background-color: lightgray
  text-align: center
  height: 100%
.icon-zone-offine
  background-color: white
  border-style: solid
  border-color: black
  border-radius: 50%
  border-width: 3px
  color: white
  display: inline-table
  height: 100px
  width: 100px
  .fas
    padding-top: 1.3rem
    text-align: center
    color: black
    font-size: 50px
    display: inline-block
.fas
  padding-top: 1.3rem
  text-align: center
  color: white
  font-size: 50px
  display: inline-block
.tag-zone
  padding: .5rem 0rem
  magin-top: 2rem
  text-align: center
  font-size: 25px
.info-zone
  background-color: #fff
  display: space-between
  text-align: center
  color: #333
  border: 2px solid transparent
  transition: 0.3s
p
  margin: 0
.more-detail
  margin-top: 2rem
  align-items: right
</style>

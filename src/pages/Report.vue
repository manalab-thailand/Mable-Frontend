<template>

  <q-page class="q-pa-sm">
    <section-header
      title="Report"
      subTitle="แสดงข้อมูลการใช้งานของ User"
    ></section-header>
  </q-page>
</template>

<script>
import SectionHeader from "../components/SectionHeader.vue";
import HistoryCard from "../components/HistoryCard.vue";
import DeviceCard from "../components/DeviceCard.vue";
export default {
  name: 'user-report',
  components: {
    SectionHeader,
    HistoryCard,
    DeviceCard
  },
  // userData: [
  //   {
  //     id: 1,
  //     name: 'Yatogami Tohka',
  //     tel: '012-345-6789',
  //     type: 'Saldanfon',
  //     location: '1202A'
  //   },
  //   {
  //     id: 2,
  //     name: 'Tobiichi Origami',
  //     tel: '987-654-3210',
  //     type: 'Metatron',
  //     location: '1202A'
  //   }
  // ]
}
</script>

<style lang="sass" scoped>
.flex-break
  display: flex
  padding: 2rem
.card-zone
  background-color: blue
  text-align: center
  height: 100%
.icon-zone
  background-color: white
  border-style: solid
  border-radius: 50%
  border-width: 3px
  color: black
  display: inline-block
  height: 100px
  width: 100px
  .fas
    padding-top: 1.3rem
    text-align: center
    color: black
    font-size: 50px
    display: inline-block
.info-zone
  background-color: lightgray
  display: inline-block
  padding: .5rem 1rem
  color: #333
  border: 2px solid transparent
  transition: 0.3s
  margin-top: 1rem
  border-radius: 15px
p
  margin: 0
.more-detail
  margin-top: 2rem
  align-items: right
</style>

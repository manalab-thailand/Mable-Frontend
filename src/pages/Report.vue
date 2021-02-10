<template>
  <div id="user-report">
    <div class="flex-break">
      <q-card class="my-card">
        <q-card-section class="card-zone">
          <div class="icon-zone">
            <i class="fas fa-file-alt"></i>
          </div>
          <div class="tag-zone">Tag {{}}</div>
          <div class="info-zone">
            <p>Name: {{}}</p>
            <p>Tel: {{}}</p>
            <p>Type: {{}}</p>
            <p>Location: {{}}</p>
          </div>
          <q-btn-dropdown
            class="more-detail"
            color="white"
            text-color="primary"
            label="..."
            size="sm"
          >
            <q-list dense>
              <q-item tag="label" to="/timeline">
                <q-item-section>Timeline</q-item-section>
              </q-item>
            </q-list>
          </q-btn-dropdown>
        </q-card-section>
      </q-card>

      <div class="grid-item"></div>
      <div class="grid-item"></div>
      <div class="grid-item"></div>
    </div>
    <div class="grid-container">
      <div class="grid-item"></div>
      <div class="grid-item"></div>
      <div class="grid-item"></div>
      <div class="grid-item"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'user-report',
  userData: [
    {
      id: 1,
      name: 'Yatogami Tohka',
      tel: '012-345-6789',
      type: 'Saldanfon',
      location: '1202A'
    },
    {
      id: 2,
      name: 'Tobiichi Origami',
      tel: '987-654-3210',
      type: 'Metatron',
      location: '1202A'
    }
  ]
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

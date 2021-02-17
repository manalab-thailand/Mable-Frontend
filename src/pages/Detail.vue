<template>
  <div>
    <div class="flex-break">
      <q-card class="my-card">
        <q-card-section class="card-zone">
          <div class="icon-zone">
            <i class="fas fa-check"></i>
          </div>
          <!-- <div class="tag-zone">Tag {{ userData[0].id }}</div>
          <div class="info-zone">
            <p>Name: {{ userData[0].name }}</p>
            <p>Tel: {{ userData[0].tel }}</p>
            <p>Type: {{ userData[0].type }}</p>
            <p>Location: {{ userData[0].location }}</p>
          </div> -->
          <q-btn-dropdown
            class="more-detail"
            color="white"
            text-color="primary"
            label="..."
            size="sm"
          >
            <q-list dense>
              <q-item tag="label" to="/detail">
                <q-item-section>Detail</q-item-section>
              </q-item>
              <q-item tag="label" to="/map">
                <q-item-section>Map</q-item-section>
              </q-item>
              <q-item tag="label">
                <q-item-section>Reset</q-item-section>
              </q-item>
            </q-list>
          </q-btn-dropdown>
        </q-card-section>
      </q-card>
    </div>
  </div>
</template>

<script>
export default {}
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
  background-color: green
  border-style: solid
  border-radius: 50%
  border-width: 3px
  color: white
  display: inline-block
  height: 100px
  width: 100px
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
.icon-zone-add
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
.tag-zone
  padding-top: .5rem
  magin-top: 2rem
  text-align: center
  font-size: 25px
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

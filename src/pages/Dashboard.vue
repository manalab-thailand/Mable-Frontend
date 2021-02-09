<template>
  <div id="user-card">
    <div class="flex-break">
      <q-card class="my-card">
        <q-card-section class="card-zone">
          <div class="icon-zone">
            <i class="fas fa-check"></i>
          </div>
          <div class="tag-zone">Tag {{ userData[0].id }}</div>
          <div class="info-zone">
            <p>Name: {{ userData[0].name }}</p>
            <p>Tel: {{ userData[0].tel }}</p>
            <p>Type: {{ userData[0].type }}</p>
            <p>Location: {{ userData[0].location }}</p>
          </div>
        </q-card-section>
      </q-card>
      <q-card class="my-card">
        <q-card-section class="card-zone">
          <div class="icon-zone">
            <i class="fas fa-check"></i>
          </div>
          <div class="tag-zone">Tag {{ userData[1].id }}</div>
          <div class="info-zone">
            <p>Name: {{ userData[1].name }}</p>
            <p>Tel: {{ userData[1].tel }}</p>
            <p>Type: {{ userData[1].type }}</p>
            <p>Location: {{ userData[1].location }}</p>
          </div>
        </q-card-section>
      </q-card>

      <q-card class="my-card">
        <q-card-section class="card-zone">
          <div class="icon-zone">
            <i class="fas fa-check"></i>
          </div>
          <div class="tag-zone">Tag {{ userData[2].id }}</div>
          <div class="info-zone">
            <p>Name: {{ userData[2].name }}</p>
            <p>Tel: {{ userData[2].tel }}</p>
            <p>Type: {{ userData[2].type }}</p>
            <p>Location: {{ userData[2].location }}</p>
          </div>
        </q-card-section>
      </q-card>

      <q-card class="my-card">
        <q-card-section class="card-zone">
          <div class="icon-zone">
            <i class="fas fa-check"></i>
          </div>
          <div class="tag-zone">Tag {{ userData[3].id }}</div>
          <div class="info-zone">
            <p>Name: {{ userData[3].name }}</p>
            <p>Tel: {{ userData[3].tel }}</p>
            <p>Type: {{ userData[3].type }}</p>
            <p>Location: {{ userData[3].location }}</p>
          </div>
        </q-card-section>
      </q-card>
    </div>
    <div class="flex-break">
      <q-card class="my-card">
        <q-card-section class="card-zone">
          <div class="icon-zone">
            <i class="fas fa-check"></i>
          </div>
          <div class="tag-zone">Tag {{ userData[4].id }}</div>
          <div class="info-zone">
            <p>Name: {{ userData[4].name }}</p>
            <p>Tel: {{ userData[4].tel }}</p>
            <p>Type: {{ userData[4].type }}</p>
            <p>Location: {{ userData[4].location }}</p>
          </div>
        </q-card-section>
      </q-card>
      <q-card class="my-card">
        <q-card-section class="card-zone-offine">
          <div class="icon-zone-offine">
            <i class="fas fa-times"></i>
          </div>
          <div class="tag-zone">Tag {{ userData[5].id }}</div>
          <div>Disconnected</div>
        </q-card-section>
      </q-card>

      <q-card class="my-card">
        <q-card-section class="card-zone">
          <div class="icon-zone">
            <i class="fas fa-check"></i>
          </div>
          <div class="tag-zone">Tag {{ userData[6].id }}</div>
          <div class="info-zone">
            <p>Name: {{ userData[6].name }}</p>
            <p>Tel: {{ userData[6].tel }}</p>
            <p>Type: {{ userData[6].type }}</p>
            <p>Location: {{ userData[6].location }}</p>
          </div>
        </q-card-section>
      </q-card>

      <q-card class="my-card">
        <q-card-section class="card-zone-offine">
          <div class="icon-zone-offine">
            <i class="fas fa-times"></i>
          </div>
          <div class="tag-zone">Tag {{ userData[7].id }}</div>
          <div>Disconnected</div>
        </q-card-section>
      </q-card>
    </div>
    <div class="flex-break">
      <q-card class="my-card">
        <q-card-section class="card-zone-offine">
          <div class="icon-zone-add">
            <i class="fas fa-plus"></i>
          </div>
          <div class="tag-zone">Add more tag</div>
        </q-card-section>
      </q-card>
      <div class="my-card"></div>
      <div class="my-card"></div>
      <div class="my-card"></div>
    </div>
  </div>
</template>

<script>
import UserDisplay from 'components/Userdisplay.vue'

export default {
  data () {
    return {
      name: 'user-card',
      components: {
        UserDisplay
      },
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
        },
        {
          id: 3,
          name: 'Himekawa Yoshino',
          tel: '987-654-3210',
          type: 'Zadkiel',
          location: '1202A'
        },
        {
          id: 4,
          name: 'Tokisaki Kurumi',
          tel: '987-654-3210',
          type: 'Zafkiel',
          location: '1202A'
        },
        {
          id: 5,
          name: 'Itsuka Kotori',
          tel: '444-444-4444',
          type: 'Camael',
          location: '1202A'
        },

        {
          id: 6,
          name: 'Kaguya Yamai',
          tel: '555-555-5255',
          type: 'Rafael',
          location: '1202A'
        },

        {
          id: 7,
          name: 'Yuzuru Yamai',
          tel: '555-555-5355',
          type: 'Rafael',
          location: '1202A'
        },

        {
          id: 8,
          name: 'Izayoi Miku',
          tel: '666-666-6166',
          type: 'Gabriel',
          location: '1202A'
        }
      ]
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
</style>

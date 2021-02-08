<template>
<div class="flex-break">
    <q-card class="my-card">
        <q-card-section>
          <div class="icon-zone">
            <i class="fas fa-check"></i>
          </div>
          <div class="tag-zone">
            {{userData[0].id}}
          </div>
          <div class="info-zone">
            {{userData[0].name}}
          </div>
        </q-card-section>
    </q-card>
    <q-card class="my-card">
        <q-card-section>
            {{userData[1].name}}
        </q-card-section>
    </q-card>
    <q-card class="my-card">
        <q-card-section>
            {{userData[2].name}}
        </q-card-section>
    </q-card>
    <q-card class="my-card">
        <q-card-section>
            {{userData[3].name}}
        </q-card-section>
    </q-card>
</div>
</template>

<script>
export default {
  data () {
    return {
      userData: [{
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
        id: 2,
        name: 'Himekawa Yoshino',
        tel: '987-654-3210',
        type: 'Metatron',
        location: '1202A'
      },
      {
        id: 2,
        name: 'Tokisaki Kurumi',
        tel: '987-654-3210',
        type: 'Metatron',
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
  max-width: 450px
  margin: 2rem
.flex-break
  display: flex
  padding: 2rem
.icon-zone
  backgrond-color:green
  border-width: 1px
  text-align: center
  height: 50px

</style>

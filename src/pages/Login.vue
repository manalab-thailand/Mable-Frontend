<template>
<div class="q-pa-md" style="max-width: 400px">
    <div>
        <div class="mt-center">
            <img class="logo-image" src="~assets/test-logo.jpg" alt="no-logo" width="50%">
        </div>
        <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="username"
        label="Username"
        hint="Username or email"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type username or email']"
      />

      <q-input
        filled
        type="password"
        v-model="password"
        label="Password"
        hint="Password"
        lazy-rules
        :rules="[
          val => val !== null && val !== '' || 'Please type your password',
          val => val.length > 8|| 'Password must be than 8 charector'
        ]"
      />
      <q-toggle v-model="save_password" label="Save password" />
      <div class="mt-center">
        <q-btn label="Login" type="submit" color="primary"/>
        <q-btn label="Forgot password" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      username: null,
      password: null,
      save_password: false
    }
  },
  methods: {
    onSubmit () {
      if (this.accept !== true) {
        this.$q.notify({
          color: 'red-5',
          textColor: 'white',
          icon: 'warning',
          message: 'You need to accept the license and terms first'
        })
      } else {
        this.$q.notify({
          color: 'green-4',
          textColor: 'white',
          icon: 'cloud_done',
          message: 'Submitted'
        })
      }
    },
    onReset () {
      this.name = null
      this.age = null
      this.accept = false
    }
  }
}
</script>

<style lang="scss" scoped>
$center: center;
.mt-center{
    text-align: $center;
}
.logo-image{
    border-radius: 50%;
    width: 50%;
    text-align: $center;
    margin-top: 50px;
    margin-bottom: 100px;
}
</style>

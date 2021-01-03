<template>
  <div class="container">
    <input v-model="userId" type="text">
    <button class="button--green" @click="onLoadUser">
      Load User
    </button>
    <div>
      <nuxt-child />
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      userId: ''
    }
  },
  methods: {
    onLoadUser () {
      this.$router.push('/users/' + this.userId)
    }
  },
  layout: 'users'
}
</script>

<style>
  .container {
    margin: 0 auto;
    min-height: 100vh;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
</style>

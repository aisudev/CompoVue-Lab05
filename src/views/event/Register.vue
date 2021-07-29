<template>
  <p>Regstration form here</p>
  <button @click="register">Register Me</button>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore'],
  methods: {
    register() {
      this.GStore.flashMessage =
        'You are succesfully register ' + this.event.title
      this.$router.push({
        name: 'EventDetails',
        params: { id: this.event.id }
      })
      setTimeout(() => {
        this.GStore.flashMessage = ''
      }, 3000)
    }
  }
}
</script>

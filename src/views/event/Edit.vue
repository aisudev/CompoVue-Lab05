<template>
  <p>Edit the event here</p>
  <button @click="edit">Edit Me</button>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore'],
  methods: {
    edit() {
      this.GStore.flashMessage = 'You are succesfully edit ' + this.event.title
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

<template>
  <span>
   <div id="remark42"></div>
  </span>
</template>

<script>
export default {
  name: "Remark",
  mounted() {
    this.$eventBus.$on('EV_SET_LIGHT_MODE', () => {
      this.setLiteTheme()
    })
    this.$eventBus.$on('EV_SET_DARK_MODE', () => {
      this.setDarkTheme()
    })
  },
  methods: {
    setDarkTheme() {
      window.REMARK42.changeTheme('dark');
    },
    setLiteTheme() {
      window.REMARK42.changeTheme('light');
    },
  },
}
</script>

<style scoped>

</style>
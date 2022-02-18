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
      console.log("light mode")
      this.setLiteTheme()
    })
    this.$eventBus.$on('EV_SET_DARK_MODE', () => {
      console.log("dark mode")
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
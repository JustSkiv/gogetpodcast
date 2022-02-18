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

    if (window.REMARK42) {
      this.initRemark42()
    } else {
      window.addEventListener('REMARK42::ready', () => {
        this.initRemark42()
      })
    }
  },
  methods: {
    initRemark42() {
      if (window.REMARK42) {
        if (this.remark42Instance) {
          this.remark42Instance.destroy()
        }

        this.remark42Instance = window.REMARK42.createInstance({
          // host: 'http://127.0.0.1:8082',
          host: 'https://remark42.gogetpodcast.ru',
          site_id: 'gogetpodcast',
          theme: 'dark',
          node: this.$refs.remark42,
        })
      }
    },
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
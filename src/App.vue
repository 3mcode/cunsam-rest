<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
import util from '@/utils/util'

export default {
  name: 'app',
  watch: {
    '$i18n.locale': 'i18nHandle'
  },
  created() {
    this.i18nHandle(this.$i18n.locale)
  },
  methods: {
    i18nHandle(val) {
      util.cookies.set('lang', val)
      document.querySelector('html').setAttribute('lang', val)
    }
  }
}
</script>

<style lang="scss">
  @import '~@/assets/style/public-class.scss';
</style>

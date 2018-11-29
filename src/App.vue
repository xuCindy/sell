<template>
  <div id="app">
    <v-header :seller="seller"></v-header>
  </div>
</template>

<script type="text/ecmascript-6">
  import { getSeller } from 'api'
  import VHeader from 'components/v-header/v-header'
  import HeaderDetail from 'components/header-detail/header-detail'

  export default {
    data () {
      return {
        seller: {}
      }
    },
    created () {
      this._getSeller()
    },
    methods: {
      _getSeller () {
        getSeller().then((seller) => {
          this.seller = seller
        })
      }
    },
    components: {
      VHeader,
      HeaderDetail
    }
  }
</script>
<style lang="stylus" rel="stylesheet/stylus">

</style>

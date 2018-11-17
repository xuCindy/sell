<template>
  <div id="app">
    <v-header :seller="seller"></v-header>
  </div>
</template>

<script type="text/ecmascript-6">
  import { getSeller } from 'api'
  import VHeader from 'components/v-header/v-header'

  export default {
    data () {
      return {
        seller: {}
      }
    },
    components: {
      VHeader
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
    }
  }
</script>
<style lang="stylus" rel="stylesheet/stylus">

</style>

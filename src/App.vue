<template>
  <!-- @touchmove.prevent阻止浏览器原生的滚动，然后用 better-scroll 模拟滚动 -->
  <div id="app" @touchmove.prevent>
    <v-header :seller="seller"></v-header>
  </div>
</template>

<script>
  import {getSeller} from 'api'
  import VHeader from "components/v-header/v-header"

  export default {
    name: "app",
    data() {
      return {
        seller: {}
      }
    },
    created() {
      this._getSeller()
    },
    methods: {
      _getSeller() {
        getSeller({
          id: this.seller.id
        }).then((seller) => {
          this.seller = Object.assign({}, this.seller, seller)
        })
      }
    },
    components: {
      VHeader
    }
  }
</script>
<style lang="stylus" scoped>
</style>

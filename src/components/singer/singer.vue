<template>
  <div>歌手页面</div>
</template>
<style lang="stylus" type="text/stylus" rel="stylesheet/stylus">
</style>
<script>
  import {getSingerList} from 'src/api/singer'
  import {ERR_OK} from 'src/api/config'

  export default{
    data(){
      return {
        singers: []
      }
    },
    created(){
      this._getSingerList()
    },
    methods: {
      _getSingerList(){
        getSingerList().then((res) => {
          if (res.code === ERR_OK) {
            this.singers = res.data.list
          }
        })

      }
    }
  }
</script>

<!-- 
 * @author miracle_dan<denghan@qianhaikeji.cn> 
-->
<template>
  <div>
    <keep-alive>
      <list v-if="showList" :list="list"></list>
    </keep-alive>
    <profile v-if="!showList"></profile>
  </div>
</template>

<script>
import { mapGetters, mapActions, mapMutations } from 'vuex'
import list from './list'
import profile from './profile'
export default {
  data(){
    return {
      list: []
    }
  },
  computed: {
    ...mapGetters({
      showList: 'isListMode'
    })
  },
  components: {
    list,
    profile
  },
  methods: {
    ...mapMutations({
      initListProfile: 'INIT_LIST_AND_PROFILE'
    })
  },
  mounted () {
    this.initListProfile()
  },
  created () {
    this.$http.get('/api/data.json').then( (res) => {
      if(res.status == 200) {
        this.list = res.data.goods
      }
    }),( error ) => {
      console.log( error )
    }
  }
}
</script>

<style scoped>
</style>

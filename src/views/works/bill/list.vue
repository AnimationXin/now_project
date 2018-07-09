<!--  -->
<template>
  <div>
    <el-row>
    <el-col :span="2"  v-for="(item,index) of list" :key="index">
      <div class="grid-content bg-purple">
        <el-button class="hidden" type="primary" @click="getfood(item.name)"> {{ item.name }}</el-button>
      </div>
    </el-col>
  </el-row>
    <chil-list :listkey="commit"></chil-list>
  </div>
</template>

<script>
import ChilList from './children'
export default {
  props: {
    list: {
      type:[Array,Object],
      default: ''
    }
  },
  data () {
    return {
      commit: [],
      flag: false
    };
  },

  components: {
    ChilList
  },

  computed: {},

  methods: {
    getfood(food) {
      let that = this
      that.list.forEach( (item,index)=>{
        if(item.name == food){
          that.commit = item
          that.flag = false
          return false
        }else{
          this.flag == true
        }
      })
      this.flag == true ? this.$message('错误') : ''
      console.log(this.commit)
    }
  }
}

</script>
<style  scoped>
.hidden{
  width: 96%;
  overflow: hidden;
  text-overflow:ellipsis;
  white-space: nowrap;
}
</style>
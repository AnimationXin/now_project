<!--  -->
<template>
  <div class="detail">
     <el-table
    :data="listkey.foods"
    style="width: 100%"
    :row-class-name="tableRowClassName">
    <el-table-column
      prop="name"
      label="名称"
      width="180">
    </el-table-column>
    <el-table-column
      prop="price"
      label="价格"
      width="180">
    </el-table-column>
    <el-table-column
      prop="rating"
      label="数量">
    </el-table-column>
     <el-table-column label="图片" width="100">
        <template scope="scope">
                   <img :src="scope.row.image" width="40" height="40" class="head_pic"/>
            </template>
    </el-table-column>
  </el-table>
  </div>
</template>

<script>
export default {
  props: {
      listkey: {
          type: [Object,Array],
          default: ''
      }
  },
  data () {
    return {
        goodslist: ''
    };
  },
  mounted(){
   this.goodslist =  this.listkey.foods
   if(this.goodslist){
       
   }
   console.log(this.goodslist)
  },
  components: {},

  computed: {

  },
  methods: {
       tableRowClassName({row, rowIndex}) {
        if (rowIndex === 1) {
          return 'warning-row';
        } else if (rowIndex === 3) {
          return 'success-row';
        }
        return '';
      }
  }
}

</script>
<style scoped>
.el-table .warning-row {
    background: oldlace;
  }

  .el-table .success-row {
    background: #f0f9eb;
  }
  .detail{
      margin-top: 10px;
  }
</style>
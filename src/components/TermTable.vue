<template>
    <div style="margin-left:80px">
      <el-col :span="4">
                           <table  class="el-table">
                               
                               <tr>
                                    <th class="el-table__row" v-for="i in tableData2" >{{i.name}}</th>
                               </tr>
                                <tr class="el-table__row--stripped">
                                  <td v-for="j in tableData2">{{j.loan}}</td>
                                  </tr>
                                  <tr class="el-table__row--stripped">
                                  <td v-for="j in tableData2">{{j.repayment}}</td>
                                  </tr>
                                   <tr class="el-table__row--stripped">
                                  <td v-for="j in tableData2">{{j.total}}</td>
                                  </tr>
                                    <tr class="el-table__row--stripped">
                                  <td v-for="j in tableData2">{{j.capital}}</td>
                                  </tr>

                           </table>
                          </el-col>
   </div>
</template>

<script>
    export default {
    
        props: ['tableData2'],
    
        data() {
    
    
    
            return {
 
                }
                 
            },
    
          computed: {
     
        },
        
        methods:{
            //copied from google
         
             
        },
       
    
    }
</script>
<style>

  .el-collapse-item__content{
      overflow-x:auto;
  }

    .el-row {
    
        margin-bottom: 20px;
    
        &:last-child {
    
            margin-bottom: 0;
    
        }
    
    }
</style>
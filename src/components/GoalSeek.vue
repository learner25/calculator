<template>
 <!--property value-->
  <div> 
      <el-row>
         <!--property value-->
          <el-col :span="6"><div class="grid-content bg-purple"></div>Property Value</el-col>
          <el-col :span="6">
            <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="input"></el-input>
                <div class="block">
                  
                  </div>
               </div>
          </el-col>
          <el-col :span="6" :offset="1">
            <div class="grid-content bg-purple">

              <div class="grid-content bg-purple-light">
                 
               </div>
            </div>
             
          </el-col>
          <el-col :span="4">
            <div class="grid-content bg-purple-light">
               <el-button type="primary" icon="plus"></el-button>
            </div>
          </el-col>
      </el-row>
      <!--annual rent-->
       <el-row>
         <!--property area-->
          <el-col :span="6"><div class="grid-content bg-purple"></div>Annual Rent</el-col>
          <el-col :span="6">
            <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="input"></el-input>
              
               </div>
          </el-col>
          <el-col :span="6" :offset="1">
            <div class="grid-content bg-purple">

              <div class="grid-content bg-purple-light">
                 
               </div>
            </div>
             
          </el-col>
          <el-col :span="4">
            <div class="grid-content bg-purple-light">
               <el-button type="primary" icon="plus"></el-button>
            </div>
          </el-col>
      </el-row>
   
         <!--Property Area-->
       <el-row>
         <!--property area-->
          <el-col :span="6"><div class="grid-content bg-purple"></div>Net Yield</el-col>
          <el-col :span="3">
            <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="input"></el-input>
                <div class="block">
                    
                     
                  </div>
               </div>
          </el-col>
          <el-col :span="2" :offset="1">
            <div class="grid-content bg-purple">

              <div class="grid-content bg-purple-light">
                    <el-input placeholder="Please input" v-model="input">
                        <template slot="prepend">YP</template>
                    </el-input>
                <div class="block">
                    
                     
                  </div>
               </div>
            </div>
                
          </el-col>
          <el-col :span="2" :offset="1">
            <div class="grid-content bg-purple-light">
                <div class="grid-content bg-purple-light">
               <el-button type="primary" icon="plus"></el-button>
            </div>
            </div>
          </el-col>
      </el-row>
       
       
     <el-row>
         
       </el-row>
    </el-row>
   </div>

</template>

<script>
 export default {
     data(){
         return {

         }
     }
 }
</script>

<style scoped>
  .el-row {
    margin-bottom: 20px;
    &:last-child {
      margin-bottom: 0;
    }
  }
</style>
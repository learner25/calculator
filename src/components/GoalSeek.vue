<template>
 <!--property value-->
  <div> 
      <el-row>
         <!--property value-->
          <el-col :span="6"><div class="grid-content bg-purple"></div>Property Value</el-col>
          <el-col :span="6">
            <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="propval"></el-input>
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
                <el-input placeholder="Please input" v-model="annualrent"></el-input>
              
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
                <el-input  v-model="net_yield"></el-input>
                <div class="block">
                    
                     
                  </div>
               </div>
          </el-col>
          <el-col :span="4" >
            <div class="grid-content bg-purple">

              <div class="grid-content bg-purple-light">
                    <el-input placeholder="Please input" v-model="yp" >
                        <template slot="prepend">YP</template>
                    </el-input>
                <div class="block">
                    
                     
                  </div>
               </div>
            </div>
                
          </el-col>
          
           
      </el-row>
           <el-row>
    
            <el-col :span="6">
    
                Mortgage(%LTV)
    
            </el-col>
    
            <el-col :span="6">
    
                <el-input placeholder="Please input" v-model="mortgagePercent"></el-input>
    
            </el-col>
    
            <el-col :span="6" :offset="1">
    
                <el-input v-model="mortgage"></el-input>
    
            </el-col>
    
        </el-row>
           <el-row>
         <el-col :span="6">
               interest rate
         </el-col>
          <el-col :span="6">
             <el-input placeholder="Please input" v-model="interestvalue"></el-input>
         </el-col>
         <el-col :span="6" :offset="1">
             <el-input placeholder="Please input" v-model="interestfullvalue">
                  
             </el-input>
         </el-col>
     </el-row>
       
         <el-row>
         <el-col :span="6">
               Interest Cover
         </el-col>
          <el-col :span="6">
             <el-input placeholder="Please input"></el-input>
         </el-col>
        
     </el-row>
      <el-row>
         <el-col :span="6">
              Required Equity
         </el-col>
          <el-col :span="6">
           
         </el-col>
         <el-col :span="6" :offset="7">
             <el-input placeholder="Please input" v-model="requireEquity">
                  
             </el-input>
         </el-col>
     </el-row>
        <el-row>
         <el-col :span="6">
              Equity Return <figcaption><small>before loan repayment</small></figcaption>
         </el-col>
          <el-col :span="6">
             <el-input placeholder="Please input" v-model="requireEquityBefore"></el-input>
         </el-col>
         <el-col :span="6" :offset="1">
             <el-input v-model="requireEquityBeforeValue">
                  
             </el-input>
         </el-col>
     </el-row>
       <el-row>
         <el-col :span="6">
              Equity Return <figcaption><small>after loan repayment</small></figcaption>
         </el-col>
          <el-col :span="6">
             <el-input placeholder="Please input" v-model="requireEquityBefore"></el-input>
         </el-col>
         <el-col :span="6" :offset="1">
             <el-input placeholder="Please input" v-model="requireEquityBeforeValue">
                  
             </el-input>
         </el-col>
     </el-row>
    </el-row>
   </div>

</template>

<script>
 export default {
     data(){
         return {
             input:''
         }
     },
     props:[
           'propval',
           'annualrent',
            'NetYieldPercent',
            'mortgage',
            'mortgagePercent',
            'interestvalue',
            'interestfullvalue',
            'requireEquity',
            'requireEquityBefore',
            'requireEquityAfter',
             'requireEquityBeforeValue',
             'yp'
           ],
 
 computed:{
     net_yield(){
         return this.NetYieldPercent;
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
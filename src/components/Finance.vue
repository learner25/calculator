<template>
    <div>
    
        <!--mortgage-->
    
        <el-row>
    
            <el-col :span="6">
    
                Mortgage(%LTV)
    
            </el-col>
    
            <el-col :span="6">
    
                <el-input placeholder="Please input" v-model="MortgagePercentageValue"></el-input>
    
            </el-col>
    
            <el-col :span="6" :offset="1">
    
                <el-input placeholder="Please input" v-model="com_mortgage_value"></el-input>
    
            </el-col>
    
        </el-row>
    
        <!--mortgage-->
    
    
    
        <!--long-term-years-->
    
        <el-row>
    
            <el-col :span="6">
    
                Loan Term (years)
    
            </el-col>
    
            <el-col :span="6">
    
                <el-input placeholder="Please input"></el-input>
    
            </el-col>
    
            <el-col :span="6" :offset="1">
    
                <el-input placeholder="Please input">
    
                    <template slot="append">Per Year
</template>
             </el-input>
         </el-col>
     </el-row>
      <!--long-term-years-->
      
      <!--Capital-->
      <el-row>
         <el-col :span="6">
              <el-select v-model="value" placeholder="Select">
                        <el-option
                        v-for="item in options"
                        :key="item.value"
                        :label="item.label"
                        :value="item.value">
                        </el-option>
                </el-select>
         </el-col>
          <el-col :span="6">
             <el-input placeholder="Please input"></el-input>
         </el-col>
         <el-col :span="6" :offset="1">
             <el-input placeholder="Please input">
                  
             </el-input>
         </el-col>
     </el-row>
      <!--Capital-->
       
       <!--interest rate-->
      <el-row>
         <el-col :span="6">
               interest rate
         </el-col>
          <el-col :span="6">
             <el-input placeholder="Please input"></el-input>
         </el-col>
         <el-col :span="6" :offset="1">
             <el-input placeholder="Please input">
                  
             </el-input>
         </el-col>
     </el-row>
      <!--interest rate-->

       <!--financial will be a collapse-->
      <el-row>
         <el-col :span="6">
               Financial Costs
         </el-col>
          <el-col :span="6">
             <el-input placeholder="Please input"></el-input>
         </el-col>
         <el-col :span="6" :offset="1">
             <el-input placeholder="Please input">
                  
             </el-input>
         </el-col>
     </el-row>
      <!--financial-->

        <!--Required entry-->
      <el-row>
         <el-col :span="6">
              Required Entity
         </el-col>
          <el-col :span="6">
           
         </el-col>
         <el-col :span="6" :offset="7">
             <el-input placeholder="Please input">
                  
             </el-input>
         </el-col>
     </el-row>
      <!--Required entry-->
     
           <!--Equity Return  before loan repayment-->
      <el-row>
         <el-col :span="6">
              Equity Return
         </el-col>
          <el-col :span="6">
             <el-input placeholder="Please input"></el-input>
         </el-col>
         <el-col :span="6" :offset="1">
             <el-input placeholder="Please input">
                  
             </el-input>
         </el-col>
     </el-row>
      <!--Equity -->

   <!--Equity Return after loan payment-->
      <el-row>
         <el-col :span="6">
              Equity Return
         </el-col>
          <el-col :span="6">
             <el-input placeholder="Please input"></el-input>
         </el-col>
         <el-col :span="6" :offset="1">
             <el-input placeholder="Please input">
                  
             </el-input>
         </el-col>
     </el-row>
      <!--Equity -->

 </div>
</template>

<script>
    export default {
    
        props: ['propertyValue'],
    
        data() {
    
    
    
            return {
    
                MortgageValue: 0,
    
                MortgagePercentageValue: 0,
    
                options: [{
    
                    value: 'Option1',
    
                    label: 'Option1'
    
                }, {
    
                    value: 'Option2',
    
                    label: 'Option2'
    
                }, {
    
                    value: 'Option3',
    
                    label: 'Option3'
    
                }, {
    
                    value: 'Option4',
    
                    label: 'Option4'
    
                }, {
    
                    value: 'Option5',
    
                    label: 'Option5'
    
                }],
    
                value: ''
    
            }
    
        },
    
        computed: {
    
            com_mortgage_value() {
    
                this.MortgageValue = this.MortgagePercentageValue * this.propertyValue * .01;
    
                return this.MortgageValue;
    
            }
    
        }
    
    }
</script>
<style>
    .el-row {
    
        margin-bottom: 20px;
    
        &:last-child {
    
            margin-bottom: 0;
    
        }
    
    }
</style>
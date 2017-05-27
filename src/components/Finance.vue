<template>
    <div>
    
        <!--mortgage-->
    
        <el-row>
    
            <el-col :span="6">
    
                Mortgage(%LTV)
    
            </el-col>
    
            <el-col :span="6">
    
                <el-input placeholder="Please input" 
                 @change="mortgage_percentage_change"
                 v-model="MortgagePercentageValue"></el-input>
    
            </el-col>
    
            <el-col :span="6" :offset="1">
    
                <el-input placeholder="Please input"
                 @change="mortgage_value_change"
                 v-model="com_mortgage_value"></el-input>
    
            </el-col>
    
        </el-row>
    
        <!--mortgage-->
    
    
    
        <!--long-term-years-->
    
        <el-row>
    
            <el-col :span="6">
    
                Loan Term (years)
            </el-col>
    
            <el-col :span="6">
    
                <el-input placeholder="Please input" v-model="LoanTermYearValue"></el-input>
    
            </el-col>
    
            <el-col :span="6" :offset="1">
    
                <el-input placeholder="Please input" v-model="com_loan_rate_in_year">
   
                    <template slot="append">Per Year
                        </template>
             </el-input>
         </el-col>
     </el-row>
      <!--long-term-years-->
        <el-row>
         <el-col :span="6">
               Loan Terms in Years
         </el-col>
          <el-col :span="13">
             <el-collapse  accordion>
                 <el-collapse-item title="show">
                    <div>
                           <el-table
                                    :data="tableData2"
                                    style="width: 100%"
                                    
                                   >
                                     <el-table-column
                                         prop="mark"
                                         label="year 2 "
                                         width="180">
                                    </el-table-column>
                                     
                                    <el-table-column
                                         prop="date"
                                         label="year 1 "
                                         width="180">
                                    </el-table-column>
                                    

                                    <el-table-column
                                         prop="name"
                                         label="year 2 "
                                         width="180">
                                     </el-table-column>
                                      <el-table-column
                                       prop="address"
                                       label="year 3">
                                    </el-table-column>
                          </el-table>
                    </div>  
                 </el-collapse-item>
             </el-collapse>
         </el-col>
     
     </el-row>
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
             <el-input placeholder="Please input" v-model="MortgagePercentageValue"></el-input>
         </el-col>
         <el-col :span="6" :offset="1">
             <el-input placeholder="Please input" v-model="com_mortgage_value">
                  
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
             <el-input placeholder="Please input"
              @change="interest_rate_percent_changes"
               v-model="InterestRateValue"></el-input>
         </el-col>
         <el-col :span="6" :offset="1">
             <el-input placeholder="Please input"
              @change="interest_rate_value_changes"
              v-model="com_interest_rate_per_year">
                  
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
             <el-input placeholder="Please input" v-model="com_financial_percent_total"></el-input>
         </el-col>
         <el-col :span="6" :offset="1">
             <el-input placeholder="Please input" v-model="com_financial_cost_total">
                  
             </el-input>
         </el-col>
     </el-row>
     <el-row>
         <el-col :span="10"  :offset="2">
         <el-col :span="4">Arrangement Fees</el-col>
         <el-col :span="4" :offset="4"><el-input v-model="ArrangeMentFeesPercentageValue"></el-input></el-col>
         <el-col :span="4" :offset="1"><el-input v-model="com_arrangement_fees"></el-input></el-col>
        </el-col>
         
          <el-col :span="10" >
         <el-col :span="4">Legal Fees</el-col>
         <el-col :span="4" :offset="4"><el-input v-model="LegalFeesPercentageValue"></el-input></el-col>
         <el-col :span="4" :offset="1"><el-input v-model="com_legal_fees"></el-input></el-col>
        </el-col>
     </el-row>

    <el-row>
         <el-col :span="10"  :offset="2">
         <el-col :span="4">Valuation Fees</el-col>
         <el-col :span="4" :offset="4"><el-input v-model="ValuationFeesPercentageValue"></el-input></el-col>
         <el-col :span="4" :offset="1"><el-input v-model="com_valuation_fees"></el-input></el-col>
        </el-col>
         
          <el-col :span="10" >
         <el-col :span="4">Other Fees</el-col>
         <el-col :span="4" :offset="4"><el-input v-model="OtherFeesPercentageValue"></el-input></el-col>
         <el-col :span="4" :offset="1"><el-input v-model="com_other_fees"></el-input></el-col>
        </el-col>
     </el-row>

      <!--financial-->

        <!--Required entry-->
      <el-row>
         <el-col :span="6">
              Required Equity
         </el-col>
          <el-col :span="6">
           
         </el-col>
         <el-col :span="6" :offset="7">
             <el-input placeholder="Please input"
              @change="required_equity_change"
              v-model="com_equity_required">
                  
             </el-input>
         </el-col>
     </el-row>
      <!--Required entry-->
     
           <!--Equity Return  before loan repayment-->
      <el-row>
         <el-col :span="6">
              Equity Return <figcaption><small>before loan repayment</small></figcaption>
         </el-col>
          <el-col :span="6">
             <el-input placeholder="Please input"
              @change="required_equity_rpbl_change"
              v-model=" com_equity_return_percentage_before_loan"></el-input>
         </el-col>
         <el-col :span="6" :offset="1">
             <el-input v-model="com_equity_return_before_loan">
                  
             </el-input>
         </el-col>
     </el-row>
      <!--Equity -->

   <!--Equity Return after loan payment-->
      <el-row>
         <el-col :span="6">
              Equity Return <figcaption><small>after loan repayment</small></figcaption>
         </el-col>
          <el-col :span="6">
             <el-input placeholder="Please input" 
                @change="required_equity_rpal_change"
             v-model=" com_equity_return_percentage_before_loan"></el-input>
         </el-col>
         <el-col :span="6" :offset="1">
             <el-input placeholder="Please input" 
               @change="required_equity_rpal_change"
             v-model="com_equity_return_after_loan">
                  
             </el-input>
         </el-col>
     </el-row>
      <!--Equity -->

 </div>
</template>

<script>
    export default {
    
        props: ['propertyValue','purchaserCost','annualRent'],
    
        data() {
    
    
    
            return {

                ArrangeMentFeesPercentageValue:0,
    
                InterestRateValue:0,
                
                MortgageValue: 0,
    
                MortgagePercentageValue: 0,

                LoanTermYearValue:0,
                ValuationFeesPercentageValue:0,
                 LegalFeesPercentageValue:0,
                OtherFeesPercentageValue:0,
                tableData2:  [{
                        date: 'xxxxxx',
                        name: 'xxxxxxx',
                        address: 'xxxxxxx',
                        year:'xxxxxxx',
                        mark:'Interest'
                        }, 
                        {
                        date: 'xxxxxxx',
                        name: 'xxxxxxx',
                        address: 'xxxxxxx',
                        mark:'Loan'
                        }, 
                        {
                        date: 'xxxxxxx',
                        name: 'xxxxxxx',
                        address: 'xxxxxxx',
                         mark:'Total'
                        },
                         {
                        date: 'xxxxxxx',
                        name: 'xxxxxxx',
                        address: 'xxxxxx',
                        mark:'Capital'
                        }],
                options: [{
    
                    value: 'Interest Only',
    
                    label: 'Interest Only'
    
                }, {
    
                    value: 'Partial Capita',
    
                    label: 'Partial Capital'
    
                },
                 {
    
                    value: 'Full Capital',
    
                    label: 'Full Capital'
    
                }, 
                 ],
    
                value: ''
    
            }
    
        },
    
        computed: {
    
            com_mortgage_value() {
    
                this.MortgageValue = this.MortgagePercentageValue * this.propertyValue * .01;
    
                return this.MortgageValue;
    
            },
            com_loan_rate_in_year(){
                return this.com_mortgage_value/ this.LoanTermYearValue
            },
            com_interest_rate_per_year(){
                return (this.InterestRateValue*this.com_mortgage_value)/100
            },
            com_arrangement_fees(){
                return (this.ArrangeMentFeesPercentageValue*this.com_mortgage_value)/100
            },
             com_legal_fees(){
                return (this.LegalFeesPercentageValue*this.com_mortgage_value)/100
            },
            com_valuation_fees(){
                 return (this.ValuationFeesPercentageValue*this.com_mortgage_value)/100
            },
            com_other_fees(){
                 return (this.OtherFeesPercentageValue*this.com_mortgage_value)/100
            },
            com_financial_cost_total(){
                return this.com_arrangement_fees+
                       this.com_legal_fees+
                       this.com_valuation_fees+
                       this.com_other_fees
            },
            com_financial_percent_total(){
                return parseFloat(this.ArrangeMentFeesPercentageValue)+
                       parseFloat(this.LegalFeesPercentageValue)+
                       parseFloat(this.ValuationFeesPercentageValue)+
                       parseFloat(this.OtherFeesPercentageValue)
            },
            com_deposit_required(){
                return this.propertyValue-this.com_mortgage_value;
            },
            com_equity_required(){
                console.log('purchaser cost in com equity ',this.purchaseCost)
                return this.com_deposit_required+this.com_financial_cost_total+this.purchaserCost;
            },
            
            com_equity_return_before_loan(){
                return Math.abs(this.com_interest_rate_per_year-this.annualRent)
            },
            com_equity_return_after_loan(){
                return Math.abs(this.com_interest_rate_per_year-this.annualRent)
            },
            com_equity_return_percentage_before_loan(){
                return this.com_equity_return_before_loan/ this.com_equity_required*100
            },

            
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
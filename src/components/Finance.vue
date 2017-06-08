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
                          <el-col :span="4">

                              <table class="el-table" style="margin-top:43px">
                                  <tr class="el-table__row--stripped">
                                   
                                  </tr>
                                   <tr class="el-table__row--stripped">
                                    <td>Interest</td>
                                  </tr>
                                  <tr class="el-table__row--stripped">
                                   <td>Repayment</td>
                                  </tr>
                                   <tr class="el-table__row--stripped">
                                  <td>Total</td>
                                  </tr>
                                   <tr class="el-table__row--stripped">
                                   <td>Capital</td>
                                  </tr>
                              </table>
                          </el-col>
                          <!--<el-col :span="4">
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
                          </el-col>-->
                          <termtable :tableData2="tableData2"></termtable>
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
             <el-input placeholder="Please input" v-model="InterestRateValue"></el-input>
         </el-col>
         <el-col :span="6" :offset="1">
             <el-input placeholder="Please input" v-model="com_interest_rate_per_year">
                  
             </el-input>
         </el-col>
     </el-row>
         <el-row>
         <el-col :span="6">
               interest cover
         </el-col>
          <el-col :span="6">
             <el-input disabled placeholder="Please input" v-model="com_interest_cover">
                 <template slot="append">%</template>
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
             <el-input placeholder="Please input" v-model="com_equity_required">
                  
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
             <el-input placeholder="Please input" v-model="com_equity_return_percentage_before_loan"></el-input>
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
             <el-input placeholder="Please input" v-model=" com_equity_return_percentage_before_loan"></el-input>
         </el-col>
         <el-col :span="6" :offset="1">
             <el-input placeholder="Please input" v-model="com_equity_return_after_loan">
                  
             </el-input>
         </el-col>
     </el-row>
      <!--Equity -->

 </div>
</template>

<script>
  import termtable from './TermTable.vue'
    export default {
    
        props: ['propertyValue','purchaserCost','annualRent','interestrate'],
        components:{termtable},
        data() {
    
    
    
            return {

                ArrangeMentFeesPercentageValue:0,
    
               InterestRateValue:0,
                
                MortgageValue: 0,
                NetAnnualRent:10000,
                MortgagePercentageValue: 0,

                LoanTermYearValue:0,
                ValuationFeesPercentageValue:0,
                LegalFeesPercentageValue:0,
                OtherFeesPercentageValue:0,
                
                tableData2:  [],
                options: [{
    
                    value: 0,
    
                    label: 'Interest Only'
    
                }, {
    
                    value: 1,
    
                    label: 'Partial Capital'
    
                },
                 {
    
                    value:2,
    
                    label: 'Full Capital'
    
                }, 
                 ],
    
                value: '',
                
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
            com_yearly_payment(){
               return this.calc_PMT(
                   this.InterestRateValue*.01,
                   10,
                  this.com_mortgage_value
               )
            },
            com_monthly_repayment(){
                return this.com_yearly_payment/12;
            },
           com_interest_cover(){
             var k = 100*this.NetAnnualRent/ parseInt(parseInt(this.com_yearly_payment)-parseInt(this.com_mortgage_value/ this.LoanTermYearValue))
             return parseInt(k)
           }
            
        },
        
        methods:{
           
           calc_PMT(interest_rate,no_of_payments,present_value)
           {
             return interest_rate * present_value * Math.pow((1 +interest_rate), no_of_payments) / (1 - Math.pow((1 + interest_rate), no_of_payments))*-1;
           },
            //out table generator
            gen_loan_terms(){

                this.tableData2 = []
                //console.log('pmt fact const',this.PMT_factor)
                let interest=this.InterestRateValue * this.com_mortgage_value*.01
                let repayment=parseInt(this.com_yearly_payment)-parseInt(this.com_interest_rate_per_year)
                let total=interest+repayment
                var temp_capital =0
                let year_1 = {
                      name:'  year 1  ',
                    interest ,
                    repayment,
                    total,
                    capital:this.com_mortgage_value-repayment 
                }
                this.tableData2.push(year_1)
                let init_term = {
                    name:'year 1',
                    interest ,
                    repayment,
                    total,
                    capital:this.com_mortgage_value-repayment
                }
                this.tableData2.push(init_term)
                console.log(init_term)
                var temp=null;
                for(let i=2;i<=parseInt(this.LoanTermYearValue);i++){
                     var  temp_loan = init_term.capital*this.InterestRateValue *.01;
                     var temp_repayment = parseInt(this.com_yearly_payment)-temp_loan
                      var temp_capital = Math.abs(init_term.capital - temp_repayment)
                          init_term.loan = parseInt(temp_loan);
                          init_term.repayment = Math.abs(parseInt(temp_repayment));
                          console.log('init capital',parseInt(temp_capital))
                          init_term.name = '  year '+i+'  ';
                         //init_term.repayment = parseInt(this.com_yearly_payment);
                         init_term.capital = parseInt(temp_capital);
                         init_term.total = total;
                        var carry=Object.assign({},init_term)
                        this.tableData2.push(carry)
                        console.log(this.tableData2)
                       
                }
                this.tableData2.splice(1,1)
            },
             
        },
        watch:{
            com_mortgage_value:function(newvalue){
               // alert('mortgage')
                 this.$emit('mortgagechange',newvalue)
              },
             InterestRateValue:function(newval){
                  this.tableData2 = []
               console.log(newval)
               if(newval>0)
               this.gen_loan_terms();
               console.log('yearly payment',parseInt(this.com_yearly_payment))
               this.$emit('interestvaluechange',newval)
           },
           com_equity_required:function(newval){
                 console.log('equity return loan')
               this.$emit('required_equity_changed',newval)
           },
           com_equity_return_percentage_before_loan:function(newval){
               console.log('equity return loan b4')
               this.$emit('required_equity_before_changed',newval)
           },
           com_equity_return_before_loan:function(newval){
               console.log('equity return loan value b4',newval)
               this.$emit('required_equity_before_value_changed',newval)
           },
           com_interest_rate_per_year:function(newval){
               console.log('loan value on capital',newval)
                 this.$emit('interest_value_changed',newval)
           },
           MortgagePercentageValue:function(newval)
           {
             console.log('mortgage percent value changed')
             console.log('computed interest cover',this.com_interest_cover)
             this.$emit('interest_cover_changed',this.com_interest_cover)
             this.$emit('mortgagePercentValuechanged',newval)
           },
           LoanTermYearValue:function(newval)
           {
               this.tableData2 = []
               console.log(newval)
               if(newval>0)
                 this.gen_loan_terms();
                 
           }
           ,
           tableData2:function(newval){
               if("length" in newval)
               {
                   console.log('length in newval','length' in newval)
                   if(newval.length>0)
                     {
                         console.log('table fill up...')
                         
                     }
               }
           },
            
        }
    
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
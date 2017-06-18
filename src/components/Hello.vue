<template>
  <div class="hello">
  
    <el-tabs type="border-card" v-model="activeName">
  
      <el-tab-pane label="Valuation" name="first">
  
        <valuation @propertyValueinput="setpropertyVal"
                   @annualRentValueinput="setAnnualRentVal"
                    @propertyAreainput="setPropertyArea"
                    @purchaserCostChange="setpurchaserCost"
                    @com_net_yield_change="com_net_yield_change"
                    @net_yield_yp_change="yp_change"
                    >
  
  
  
        </valuation>
  
      </el-tab-pane>
  
      <el-tab-pane label="Finance" name="second">
  
        <finance :propertyValue="propertyVal"
                  :purchaserCost="purchaserCost"
                  :annualRent="annualrentVal"
                 @mortgagechange="catchmortgage"
                 @interestvaluechange="catchinterestvalue"
                 @required_equity_changed="equity_return_set"
                 @required_equity_before_changed="equity_return_before_set"
                 @required_equity_before_value_changed="equity_return_before_value_set"
                 @interest_value_changed="set_interest_full_value"
                 @mortgagePercentValuechanged="set_mortgage_percent_value"
                 @interest_cover_changed="set_interest_cover"
         >
  
  
  
        </finance>
  
      </el-tab-pane>
  
      <el-tab-pane label="Goal Seek" name="third">
  
        <goal :propval="propertyVal" 
         :annualrent="annualrentVal"
         :NetYieldPercent = "netyield"
         :mortgage="mortgage"
         :interestvalue="interestvalue"
         :requireEquity="equity_return"
         :requireEquityBefore="equity_return_before"
         :requireEquityBeforeValue="equity_return_before_value"
         :interestfullvalue="interest_full_value"
         :mortgagePercent = "mortgage_percent"
         :yp="yp_val"
         :interestCover = "interest_cover"
        ></goal>
  
      </el-tab-pane>
  
       <el-tab-pane label="stamp" name="stamp">
         <multistamp
         :propertyValue="parseInt(propertyVal)"
         ></multistamp>
         <stamp
          :propertyValue="parseInt(propertyVal)"
         ></stamp>
         <commercialStampDuty
          :propertyValue="parseInt(propertyVal)"
         ></commercialStampDuty>
      </el-tab-pane>
        
    </el-tabs>
  
  </div>
</template>

<script>
  import stamp from './StampDuty/singleStampDuty.vue'
  import multistamp from './StampDuty/MultiStampDuty.vue'
  import commercialStampDuty from './StampDuty/CommercialStampDuty.vue'
  import finance from './Finance.vue'
  import valuation from './Valuation.vue'
  import goal from './GoalSeek.vue'
  export default {
  
    name: 'hello',
  
    components: {
  
      finance,
  
      valuation,
  
      goal,
    
      stamp,
      multistamp,
      commercialStampDuty
  
    },
  
    data() {
  
      return {
  
        msg: 'Welcome to Your Vue.js App',
  
        input: '',
        activeName:"first",
        value8: 8,
        netyield:0,
        propertyVal: 0,
        yp_val:0,
        annualrentVal: 0,
        mortgage:0,
        propertyArea: 0,
        purchaserCost:0,
        interestvalue:0,
        interest_full_value:0,
        equity_return:0,
        equity_return_before:0,
        equity_return_before_value:0,
        mortgage_percent:0,
        interest_cover:0
      }
  
    },
  
    methods: {
  
      setpropertyVal(data) {
  
        this.propertyVal = data;
  
     },
  
      setAnnualRentVal(data) {
  
        this.annualrentVal = data;
  
     },
      yp_change(data){
           console.log('yp...',data)
           this.yp_val = data
      },
      setPropertyArea(data) {
       this.propertyArea = data;
       },
      setpurchaserCost(data)
      {
        this.purchaserCost=data;
      },
      com_net_yield_change(data)
      {
       this.netyield = data
      },
      catchmortgage(data){
        
        console.log('mortgage spat')
         this.mortgage = data
      },
      catchinterestvalue(data)
      {
        //alert(data)
        this.interestvalue = data;
      },
     equity_return_set(data)
     {
       this.equity_return = data;
     },
     set_interest_cover(data)
     {
        // alert('interest cover',data)
         this.interest_cover = data
     },
     equity_return_before_set(data)
     {
       console.log('equity return before set',data)
       this.equity_return_before=data
     },
     equity_return_before_value_set(data)
     {
       console.log('before value from finance in goal')
       if(isNaN(data)) alert('nan')
       this.equity_return_before_value = data;
     },
     set_interest_full_value(data){
        this.interest_full_value = data
     },
     set_mortgage_percent_value(data)
     {
       this.mortgage_percent = data
     }
    }
  
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1,
  
  h2 {
  
    font-weight: normal;
  
  }
  
  
  
  ul {
  
    list-style-type: none;
  
    padding: 0;
  
  }
  
  
  
  li {
  
    display: inline-block;
  
    margin: 0 10px;
  
  }
  
  
  
  a {
  
    color: #42b983;
  
  }
  
  
  
  .el-row {
  
    margin-bottom: 20px;
  
    &:last-child {
  
      margin-bottom: 0;
  
    }
  
  }
</style>

<template>
  <div class="hello">
  
    <el-tabs type="border-card">
  
      <el-tab-pane label="Valuation" name="first">
  
        <valuation @propertyValueinput="setpropertyVal"
                   @annualRentValueinput="setAnnualRentVal"
                    @propertyAreainput="setPropertyArea"
                    @purchaserCostChange="setpurchaserCost"
                    >
  
  
  
        </valuation>
  
      </el-tab-pane>
  
      <el-tab-pane label="Finance" name="second">
  
        <finance :propertyValue="propertyVal"
                  :purchaserCost="purchaserCost"
         >
  
  
  
        </finance>
  
      </el-tab-pane>
  
      <el-tab-pane label="Goal Seek" name="third">
  
        <goal :propval="propertyVal" :annualrent="annualrentVal"></goal>
  
      </el-tab-pane>
  
  
  
    </el-tabs>
  
  </div>
</template>

<script>
  import finance from './Finance.vue'
  
  import valuation from './Valuation.vue'
  
  import goal from './GoalSeek.vue'
  
  export default {
  
    name: 'hello',
  
    components: {
  
      finance,
  
      valuation,
  
      goal
  
    },
  
    data() {
  
      return {
  
        msg: 'Welcome to Your Vue.js App',
  
        input: '',
  
        value8: 8,
  
        propertyVal: 0,
  
        annualrentVal: 0,
  
        propertyArea: 0,
        purchaserCost:0
  
      }
  
    },
  
    methods: {
  
      setpropertyVal(data) {
  
        this.propertyVal = data;
  
  
  
      },
  
      setAnnualRentVal(data) {
  
        this.annualrentVal = data;
  
  
  
      },
  
      setPropertyArea(data) {
  
  
  
        this.propertyArea = data;
  
      },
      setpurchaserCost(data)
      {
        this.purchaserCost=data;
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




<template>
  <!--property value-->
  
  <div>
  
    <el-row>
  
      <!--property value-->
  
      <el-col :span="6">
  
        <div class="grid-content bg-purple"></div>Property Value</el-col>
  
      <el-col :span="6">
  
        <div class="grid-content bg-purple-light">
  
          <el-input v-model="propertyValue" v-on:change="propvalchng()"></el-input>
  
          <div class="block">
  
            <el-slider v-model="propertyValue" :step="10" :max="2000" @change="propvalchng()">
  
            </el-slider>
  
  
  
          </div>
  
        </div>
  
      </el-col>
  
      <el-col :span="6" :offset="1">
  
        <div class="grid-content bg-purple">
  
  
  
          <div class="grid-content bg-purple-light">
  
            <el-input placeholder="Please input" v-model="perUnit" :value="perUnit" disabled></el-input>
  
            <div class="block">
  
              <el-slider v-model="value8" :step="10" :max="2000">
  
              </el-slider>
         
             </div>
  
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
  
      <el-col :span="6">
  
        <div class="grid-content bg-purple"></div>Annual Rent</el-col>
  
      <el-col :span="6">
  
        <div class="grid-content bg-purple-light">
  
          <el-input placeholder="Please input" @change="annualRentchng()" v-model="annualRentValue"></el-input>
  
          <div class="block">
  
            <el-slider v-model="annualRentValue" :step="10" :max="2000" @change="annualRentchng()">
  
            </el-slider>
  
  
  
          </div>
  
        </div>
  
      </el-col>
  
      <el-col :span="6" :offset="1">
  
        <div class="grid-content bg-purple">
  
  
  
          <div class="grid-content bg-purple-light">
  
            <el-input placeholder="Please input" v-model="anual_rent_perUnit" :value="perUnit" disabled></el-input>
  
            <div class="block">
  
              <el-slider v-model="value8" :step="10" :max="2000">
  
              </el-slider>
  
  
  
            </div>
  
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
  
      <el-col :span="6">
  
        <div class="grid-content bg-purple"></div>Property Area</el-col>
  
      <el-col :span="6">
  
        <div class="grid-content bg-purple-light">
  
          <el-input placeholder="Please input" @change="areachange()" v-model="propertyArea"></el-input>
  
          <div class="block">
  
            <el-slider :step="10" :max="2000" @change="areachange()" v-model="propertyArea">
  
            </el-slider>
  
  
  
          </div>
  
        </div>
  
      </el-col>
  
      <el-col :span="6" :offset="1">
  
        <div class="grid-content bg-purple">
  
  
  
          <div class="grid-content bg-purple-light">
  
  
  
            <el-select v-model="unit" placeholder="Select">
  
              <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value">
  
              </el-option>
  
            </el-select>
  
          </div>
  
        </div>
  
  
  
      </el-col>
  
      <el-col :span="4">
  
        <div class="grid-content bg-purple-light">
  
  
  
        </div>
  
      </el-col>
  
    </el-row>
  
  
  
    <el-row>
  
      <el-collapse accordion>
  
        <el-collapse-item name="1">
  
          <template slot="title">
  
        Purchase Costs
</template>
          <el-row>
         <!--property value-->
          <el-col :span="6"><div class="grid-content bg-purple"></div>Purchaser Cost</el-col>
          <el-col :span="6">
            <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input"
                 @change="purchaserCostChange"
                 v-model="purchaserCost"></el-input>
                <div class="block">
                     
                     
                  </div>
               </div>
          </el-col>
          <el-col :span="6" :offset="1">
            <div class="grid-content bg-purple">

              <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" 
                v-model="purchaseCostPercentage"
                disabled
                ></el-input>
                <div class="block">
                    
                     
                  </div>
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
          <el-col :span="6"><div class="grid-content bg-purple"></div>Stamp Duty</el-col>
          <el-col :span="6">
            <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="stampDuty" disabled></el-input>
                <div class="block">
                 
                     
                  </div>
               </div>
          </el-col>
          <el-col :span="6" :offset="1">
            <div class="grid-content bg-purple">

              <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="propertyArea"></el-input>
                <div class="block">
                    <el-slider
                      v-model="value8"
                      :step="10"
                      :max="2000"
                      >
                    </el-slider>
                     
                  </div>
               </div>
            </div>
             
          </el-col>
          <el-col :span="4">
            <div class="grid-content bg-purple-light">
               <el-button type="primary" icon="plus"></el-button>
            </div>
          </el-col>
      </el-row>
          <el-row>
         <!--agency fees-->
          <el-col :span="6"><div class="grid-content bg-purple"></div>Legal Fees</el-col>
          <el-col :span="6">
            <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="com_legal_fees" disabled></el-input>
                <div class="block">
                 
                     
                  </div>
               </div>
          </el-col>
          <el-col :span="6" :offset="1">
            <div class="grid-content bg-purple">

              <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="propertyArea"></el-input>
                <div class="block">
                    <el-slider
                      v-model="value8"
                      :step="10"
                      :max="2000"
                      >
                    </el-slider>
                     
                  </div>
               </div>
            </div>
             
          </el-col>
          <el-col :span="4">
            <div class="grid-content bg-purple-light">
               <el-button type="primary" icon="plus"></el-button>
            </div>
          </el-col>
      </el-row>
        <el-row>
         <!--legal fees-->
          <el-col :span="6"><div class="grid-content bg-purple"></div>Agency Fees</el-col>
          <el-col :span="6">
            <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="com_agency_fees" disabled></el-input>
                <div class="block">
                 
                     
                  </div>
               </div>
          </el-col>
          <el-col :span="6" :offset="1">
            <div class="grid-content bg-purple">

              <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="propertyArea"></el-input>
                <div class="block">
                    <el-slider
                      v-model="value8"
                      :step="10"
                      :max="2000"
                      >
                    </el-slider>
                     
                  </div>
               </div>
            </div>
             
          </el-col>
          <el-col :span="4">
            <div class="grid-content bg-purple-light">
               <el-button type="primary" icon="plus"></el-button>
            </div>
          </el-col>
      </el-row>
          </el-collapse-item>
        </el-collapse>
       </el-row>
          
           <el-row :gutter="20">
  <el-col :span="6"><div class="grid-content bg-purple">Gross Value</div></el-col>
  <el-col :span="6"><div class="grid-content bg-purple">{{parseFloat(propertyValue)+parseFloat(com_gross)}}</div></el-col>
  <el-col :span="6"><div class="grid-content bg-purple"> </div></el-col>
  <el-col :span="6"><div class="grid-content bg-purple"> </div></el-col>
</el-row>
                <el-row :gutter="20">
  <el-col :span="6">
     <div class="grid-content bg-purple">
        Net Yield
        </div>
        </el-col>
  <el-col :span="6">
    <div class="grid-content bg-purple">
    <el-input v-model="com_net_yield" >
      </el-input></div>
      </el-col>
  <el-col :span="6"><div class="grid-content bg-purple"> 
    <el-input placeholder="Please input" v-model="com_net_yield_yp" disabled>
<template slot="prepend">
  YP
</template>
  </el-input></div>
  </el-col>
  <el-col :span="6"><div class="grid-content bg-purple"><el-button type="primary" icon="plus"></el-button> </div></el-col>
</el-row>
     <el-row>
         <el-collapse accordion>
          <el-collapse-item name="1">
<template slot="title">
   Yield Sensitivity
</template>
        <!--row 1-->
          <el-row>
         <!--property value-->
          
          <div class="block">
           <el-col :span="4" :offset="10">
              <el-input v-model="YieldSensitivityIncreamentValue">
<template slot="append">
  %
</template>
              </el-input>
                    <el-slider
                      v-model="YieldSensitivityIncreamentValue"
                      :step="0.010"
                      :max="1000"
                      >
                    </el-slider>
                     <div>{{YieldSensitivityIncreamentValue}}%</div>
                  
           </el-col>
           </div>
          </el-row>
          <el-row>
            <!--year 1-->
          <el-col :span="4"><div class="grid-content bg-purple">
              <el-input placeholder="Please input" v-model="com_y1_sensitivity">
                </el-input>
                </div>
                </el-col>
                <!--year 2-->
          <el-col :span="4">
            <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="com_y2_sensitivity"></el-input>
                <div class="block">
                     
                  </div>
               </div>
          </el-col>
          <!--year 3-->
          <el-col :span="4" :offset="1">
            <div class="grid-content bg-purple">

              <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="com_net_yield"></el-input>
                <div class="block">
                  </div>
               </div>
            </div>
              
          </el-col>
          <!--year 4-->
          <el-col :span="4">
            <div class="grid-content bg-purple-light">
               <el-input placeholder="Please input" v-model="com_y4_sensitivity"></el-input>
            </div>
          </el-col>
          <!--year 5-->
          <el-col :span="4">
            <div class="grid-content bg-purple-light">
               <el-input placeholder="Please input" v-model="com_y5_sensitivity"></el-input>
            </div>
          </el-col>
      </el-row>
      <!--row 2-->
         <el-row>
         <!--year 6-->
          <el-col :span="4"><div class="grid-content bg-purple">
              <el-input placeholder="Please input" v-model="input">
                </el-input>
                </div>
                </el-col>
                 <!--year 7-->
          <el-col :span="4">
            <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="input"></el-input>
                <div class="block">
                     
                  </div>
               </div>
          </el-col>
           <!--year 8-->
          <el-col :span="4" :offset="1">
            <div class="grid-content bg-purple">

              <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="propertyValue"></el-input>
                <div class="block">
                  </div>
               </div>
            </div>
              
          </el-col>
           <!--year 9-->
          <el-col :span="4">
            <div class="grid-content bg-purple-light">
               <el-input placeholder="Please input" v-model="propertyValue"></el-input>
            </div>
          </el-col>
          <!--year 10-->
          <el-col :span="4">
            <div class="grid-content bg-purple-light">
               <el-input placeholder="Please input" v-model="propertyValue"></el-input>
            </div>
          </el-col>
      </el-row>
          </el-collapse-item>
        </el-collapse>
       </el-row>
    </el-row>
   </div>

</template>

<script>

  export default {
  
    data() {
  
      return {
  
        value8: 8,
  
        input: '',
  
        input3: '',
  
        propertyValue: 0,
  
        propertyArea: 0,
  
        annualRentValue: 0,
        stampDuty:0,
        NetYield: 0,
  
        YieldSensitivityIncreamentValue: 0,
  
        purchaseCostPercentage: 1.80,
  
        LegalFees: 0,
  
        LegalFeesPercentage: 0.075,

        LoanTermsYearValue:0,
  
        AgencyFees: 1,
  
        unit: 'Sq Meters',
  
        options: [{
  
          value: 'Sq Meters',
  
          label: 'Sq Meters'
  
        }, {
  
          value: 'Sq Feet',
  
          label: 'Sq Feet'
  
        }, ],
  
        value: ''
  
      }
  
    },
  
  
  
    computed: {
  
     comp_ps_properVal() {
  
        if (this.__ispa === true) {
  
         return this.propertyValue / this.propertyArea;
  
        } else
  
          return 0;
  
      },
  
      comp_ps_annualRent() {
  
        if (this.__ispa)
  
          return this.annualRentValue / this.propertyArea;
  
        else
  
          return 0;
  
      },
  
      comp_ps_property_value() {
  
        return 0;
  
      },
  
      perUnit() {
  
        return this.comp_ps_properVal + ' $' + this.unit;
  
      },
  
      anual_rent_perUnit() {
  
        return this.comp_ps_annualRent + ' $' + this.unit;
  
      },
  
      __ispa() {
  
        if (this.propertyArea !== undefined || this.propertyArea != null || this.propertyArea != 0)
  
          return true;
  
        else
  
          return false;
  
      },
  
      purchaserCost() {
  
        return this.propertyValue * this.purchaseCostPercentage * .01;
  
      },
  
      com_legal_fees() {
  
        return this.propertyValue * this.LegalFeesPercentage * .1;
  
      },
  
      com_agency_fees() {
  
        return this.propertyValue * .01 * 1;
  
      },
  
      com_gross() {
  
        return this.com_legal_fees +
  
          this.com_agency_fees +
  
          this.com_agency_fees
  
      },
  
      com_net_yield() {
  
        console.log("annual rent", this.annualRentValue)
  
        console.log("gross", this.propertyValue + this.com_gross)
  
        return 100 * (this.annualRentValue / (parseFloat(this.propertyValue) + parseFloat(this.com_gross))) + "%";
  
      },
       com_net_yield_yp() {
  
        console.log("annual rent", this.annualRentValue)
  
        console.log("gross", this.propertyValue + this.com_gross)
  
        return ( (parseFloat(this.propertyValue) + parseFloat(this.com_gross))/ this.annualRentValue) + "%";
  
      },
  
      com_y1_sensitivity() {
  
        var d = 100 * (this.annualRentValue / (parseFloat(this.propertyValue) + parseFloat(this.com_gross)));
  
        return d - 2 * this.YieldSensitivityIncreamentValue + "%";
  
      },
  
      com_y2_sensitivity() {
  
        var d = 100 * (this.annualRentValue / (parseFloat(this.propertyValue) + parseFloat(this.com_gross)));
  
        return d - this.YieldSensitivityIncreamentValue + "%";
  
      },
  
      com_y4_sensitivity() {
  
        var d = 100 * (this.annualRentValue / (parseFloat(this.propertyValue) + parseFloat(this.com_gross)));
  
        return d + this.YieldSensitivityIncreamentValue + "%";
  
      },
  
      com_y5_sensitivity() {
  
        var d = 100 * (this.annualRentValue / (parseFloat(this.propertyValue) + parseFloat(this.com_gross)));
  
        return d + 2 * this.YieldSensitivityIncreamentValue + "%";
  
      },
  
    },
  
    methods: {
  
      propvalchng() {
  
        this.$emit('propertyValueinput', this.propertyValue)
  
      },
  
      annualRentchng() {
  
        this.$emit('annualRentValueinput', this.annualRentValue)
  
      },
      com_net_yield_change(){
         console.log('net yield update...',)
        
        
      },
      areachange() {
  
        this.$emit('propertyAreainput', this.propertyArea)
  
      },
     purchaserCostChange(){
        this.$emit('purchaserCostChange', this.purchaserCost)
     }
  
  
    },
    watch :{
      com_net_yield:function(newval){
           this.$emit('com_net_yield_change',newval)
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
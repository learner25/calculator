


<template>
  <!--property value-->
  
  <div>
  
    <el-row>
  
      <!--property value-->
  
      <el-col :span="6">
  
        <div class="grid-content bg-purple"></div>Property Value</el-col>
  
      <el-col :span="6">
  
        <div class="grid-content bg-purple-light">
  
          <el-input  v-model.trim.number="propertyValue" v-on:change="propvalchng()"></el-input>
  
          <div class="block">
  
            <el-slider v-model="propertyValue" :step="1000" :max="200000" >
  
            </el-slider>
          </div>
  
        </div>
  
      </el-col>
  
      <el-col :span="6" :offset="1">
  
        <div class="grid-content bg-purple">
  
  
  
          <div class="grid-content bg-purple-light">
  
            <el-input placeholder="Please input" v-model.trim.number="perUnit" ></el-input>
  
            <div class="block">
  
              <el-slider v-model="perUnit" :step="10" :max="20000">
  
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
  
          <el-input placeholder="Please input" @change="annualRentchng()" v-model.trim.number="annualRentValue"></el-input>
  
          <div class="block">
  
            <el-slider v-model="annualRentValue" :step="10" :max="2000" @change="annualRentchng()">
  
            </el-slider>
  
  
  
          </div>
  
        </div>
  
      </el-col>
  
      <el-col :span="6" :offset="1">
  
        <div class="grid-content bg-purple">
  
  
  
          <div class="grid-content bg-purple-light">
  
            <el-input placeholder="Please input" v-model="anual_rent_perUnit"   disabled></el-input>
  
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
  
          <el-input placeholder="Please input" @change="areachange()" v-model.trim.number="propertyArea"></el-input>
  
          <div class="block">
  
            <el-slider :step="10" :max="2000" @change="areachange()" v-model="propertyArea">
  
            </el-slider>
  
  
  
          </div>
  
        </div>
  
      </el-col>
  
      <el-col :span="6" :offset="1">
  
        <div class="grid-content bg-purple">
  
  
  
          <div class="grid-content bg-purple-light">
  
  
  
            <el-select v-model="unit" placeholder="Select" @change="unitchange">
  
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
                <el-input placeholder="Please input" v-model.trim.number="com_legal_fees" disabled></el-input>
                <div class="block">
                 
                     
                  </div>
               </div>
          </el-col>
          <el-col :span="6" :offset="1">
            <div class="grid-content bg-purple">

              <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model.trim.number="com_legal_fees"></el-input>
                <div class="block">
                    <el-slider
                      v-model="com_legal_fees"
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
                <el-input placeholder="Please input" v-model.trim.number="propertyArea"></el-input>
                <div class="block">
                    <el-slider
                      v-model="propertyArea"
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
        propertyValue:0,
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
        unit: '0',
  
        options: [{
  
          value: 0,
  
          label: 'Sq Meters'
  
        }, {
  
          value: 1,
  
          label: 'Sq Feet'
  
        }, ],
  
        value: ''
  
      }
  
    },
  
  
  
    computed: {
  
     comp_ps_properVal() {
  
        if (this.__ispa == true) {
      
        var d = this.propertyValue / this.propertyArea;
        console.log('d da d',d)
        if(!isNaN(d) && isFinite(d)) return d;
         else return 0;
        } 
  
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
        if(!this.__ispa)
        {
          return 0;
        }
       else  if(this.unit=='0') {
         console.log('per unit area triggerd')
        // this.propertyArea /=10.76;
        var c = parseInt(this.comp_ps_properVal) /10.76;
         return parseFloat(c)  ;
        }
        else {
           
           //this.propertyArea *=10.76;
          this.comp_ps_properVal*=10.76;
           return this.comp_ps_properVal + ' $ Sq.Meter' ;
        }
        
  
      },
  
      anual_rent_perUnit() {
        if(!isNaN(this.comp_ps_annualRent) && isFinite(this.comp_ps_annualRent))
        return this.comp_ps_annualRent + ' $ sq Feet' ;
        else 
        return 0;
      },
  
      __ispa() {
  
        if (this.propertyArea !== undefined || this.propertyArea != null || this.propertyArea != 0||
          !isNaN(this.propertyArea)||isFinite(this.propertyArea))
  
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
  
        var d= 100 * (this.annualRentValue / (parseFloat(this.propertyValue) + parseFloat(this.com_gross))) + "%";
         if(isFinite(parseFloat(d))||!isNaN(d)) return d;
          else return 0;
         
      },
       com_net_yield_yp() {
        console.log("annual rent", this.annualRentValue)
        console.log("gross", this.propertyValue + this.com_gross)
        var d = ( (parseFloat(this.propertyValue) + parseFloat(this.com_gross))/ this.annualRentValue) + "%";
         if(isFinite(parseFloat(d))) return d;
          else return 0;
      },
  
      com_y1_sensitivity() {
  
        var d = 100 * (this.annualRentValue / (parseFloat(this.propertyValue) + parseFloat(this.com_gross)));
        var k = Math.abs(d - 2 * this.YieldSensitivityIncreamentValue);
        if(!isNaN(k)||isFinite(k)) return k+"%";
        return  0;
  
      },
  
      com_y2_sensitivity() {
  
        var d = 100 * (this.annualRentValue / (parseFloat(this.propertyValue) + parseFloat(this.com_gross)));
  
       var c =  Math.abs(d - this.YieldSensitivityIncreamentValue) ;
       if(!isNaN(c)||isFinite(c))
        return c+ "%";

       return 0;
  
      },
  
      com_y4_sensitivity() {
  
        var d = 100 * (this.annualRentValue / (parseFloat(this.propertyValue) + parseFloat(this.com_gross)));
  
        var j = Math.abs(d + this.YieldSensitivityIncreamentValue);
        if(!isNaN(j)||isFinite(j)) return j + "%";
         return 0;
  
      },
  
      com_y5_sensitivity() {
  
        var d = 100 * (this.annualRentValue / (parseFloat(this.propertyValue) + parseFloat(this.com_gross)));
  
        var c = Math.abs(d + 2 * this.YieldSensitivityIncreamentValue);
        if(!isNaN(c)||isFinite(c)) return c + "%";
         return 0;
  
      },
  
    },
  
    methods: {
      unitchange(){
           if(!this.__ispa)
        {
          return 0;
        }
       else  if(this.unit==0 && this.__ispa) {
         var p= this.propertyArea /10.76;
         return this.comp_ps_properVal + ' $' + this.unit;
        }
        else {
           if(this.__ispa)
           var g = this.propertyArea *10.76;
           return (this.comp_ps_properVal *10.76)+ ' $' + this.unit;
        }
      },
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
      },
      com_net_yield_yp:function(newval){
        this.$emit('net_yield_yp_change',newval)
      }
    },
    updated(){
      console.log('updating dom')
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
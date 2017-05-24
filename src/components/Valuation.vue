<template>
 <!--property value-->
  <div> 
      <el-row>
         <!--property value-->
          <el-col :span="6"><div class="grid-content bg-purple"></div>Property Value</el-col>
          <el-col :span="6">
            <div class="grid-content bg-purple-light">
                <el-input  v-model="propertyValue" v-on:change="propvalchng()"></el-input>
                <div class="block">
                    <el-slider
                      v-model="propertyValue"
                       :step="10"
                      :max="2000"
                     @change="propvalchng()"
                      >
                    </el-slider>
                     
                  </div>
               </div>
          </el-col>
          <el-col :span="6" :offset="1">
            <div class="grid-content bg-purple">

              <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" 
                 v-model="perUnit"
                 :value="perUnit"
                   disabled
                 ></el-input>
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
      <!--annual rent-->
       <el-row>
         <!--property area-->
          <el-col :span="6"><div class="grid-content bg-purple"></div>Annual Rent</el-col>
          <el-col :span="6">
            <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input"
                 @change="annualRentchng()"
                 v-model="annualRentValue"></el-input>
                <div class="block">
                    <el-slider
                      v-model="annualRentValue"
                      :step="10"
                      :max="2000"
                      @change="annualRentchng()"
                      >
                    </el-slider>
                     
                  </div>
               </div>
          </el-col>
          <el-col :span="6" :offset="1">
            <div class="grid-content bg-purple">

              <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input"
                  v-model="anual_rent_perUnit"
                 :value="perUnit"
                 disabled
                ></el-input>
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
   
         <!--Property Area-->
       <el-row>
         <!--property area-->
          <el-col :span="6"><div class="grid-content bg-purple"></div>Property Area</el-col>
          <el-col :span="6">
            <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" @change="areachange()" v-model="propertyArea"></el-input>
                <div class="block">
                    <el-slider
                      
                      :step="10"
                      :max="2000"
                       @change="areachange()"
                        v-model="propertyArea"
                      >
                    </el-slider>
                     
                  </div>
               </div>
          </el-col>
          <el-col :span="6" :offset="1">
            <div class="grid-content bg-purple">

              <div class="grid-content bg-purple-light">
              
                 <el-select v-model="unit" placeholder="Select">
                      <el-option
                        v-for="item in options"
                        :key="item.value"
                        :label="item.label"
                        :value="item.value">
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
                <el-input placeholder="Please input" v-model="purchaserCost"></el-input>
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
  <el-col :span="6"><div class="grid-content bg-purple">Net Yield</div></el-col>
  <el-col :span="6"><div class="grid-content bg-purple"><el-input></el-input></div></el-col>
  <el-col :span="6"><div class="grid-content bg-purple"> 
    <el-input placeholder="Please input" disabled v-model="input3">
    <template slot="prepend">YP</template>
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
          <el-row>
         <!--property value-->
          <el-col :span="6"><div class="grid-content bg-purple"></div>Property Value</el-col>
          <el-col :span="6">
            <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="propertyValue"></el-input>
                <div class="block">
                    <el-slider
                      v-model="value8"
                      :step="10"
                      :max="2000"
                      >
                    </el-slider>
                     
                  </div>
               </div>
          </el-col>
          <el-col :span="6" :offset="1">
            <div class="grid-content bg-purple">

              <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="input"></el-input>
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
      <!--annual rent-->
       <el-row>
         <!--property area-->
          <el-col :span="6"><div class="grid-content bg-purple"></div>Annual Rent</el-col>
          <el-col :span="6">
            <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input"
                 @change="areachange"
                 v-model="annualRentValue"></el-input>
                <div class="block">
                    <el-slider
                      v-model="annualRentValue"
                      :step="10"
                      :max="2000"
                      >
                    </el-slider>
                     
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
    </el-row>
   </div>

</template>

<script>
 export default {
     data(){
         return {
           value8:8,
           input:'',
           input3:'',
           propertyValue:0,
           propertyArea:0,
           annualRentValue:0,
           purchaseCostPercentage:1.80,
           LegalFees:0,
           LegalFeesPercentage:0.075,
           AgencyFees:1,
           unit:'Sq Meters',
            options: [{
          value: 'Sq Meters',
          label: 'Sq Meters'
        }, {
          value: 'Sq Feet',
          label: 'Sq Feet'
        },
        ],
        value: ''
         }
     },
      
     computed:{
      
       comp_ps_properVal(){
         if(this.__ispa===true){
            
            return this.propertyValue / this.propertyArea;
         }
         else 
          return 0;
       },
         comp_ps_annualRent(){
            if(this.__ispa)
             return this.annualRentValue/ this.propertyArea;
           else
           return 0;
       },
      comp_ps_property_value(){
        return 0;
      },
        perUnit(){
          return this.comp_ps_properVal+' $'+this.unit;
      },
        anual_rent_perUnit(){
          return this.comp_ps_annualRent+' $'+this.unit;
      },
      __ispa(){
        if(this.propertyArea!==undefined || this.propertyArea!=null ||this.propertyArea!=0)
             return true;
        else
         return false;
      },
      purchaserCost(){
        return this.propertyValue*this.purchaseCostPercentage*.01;
      },
      com_legal_fees(){
        return  this.propertyValue*this.LegalFeesPercentage*.1;
      },
      com_agency_fees(){
        return this.propertyValue*.01*1;
      },
      com_gross(){
        return this.com_legal_fees+
               this. com_agency_fees+
               this. com_agency_fees
      }
     },
     methods:{
       propvalchng(){
         this.$emit('propertyValueinput',this.propertyValue)
       },
        annualRentchng(){
         this.$emit('annualRentValueinput',this.annualRentValue)
       },
       areachange(){
         this.$emit('propertyAreainput',this.propertyArea)
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
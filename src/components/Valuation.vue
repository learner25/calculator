<template>
    <!--property value-->
    <div>
        <el-row>
            <!--property value-->
            <el-col :span="6" >
                <div class="grid-content bg-purple">Property Value</div>
            </el-col>

            <el-col :span="4">
                <div class="grid-content bg-purple-light">
                    <el-input  v-model.trim.number="propertyValue" @change="propvalchng()">
                        <template slot="prepend">(£) </template>
                    </el-input>
                    <div class="block">
                        <el-slider v-model="propertyValue" 
                         :steps="10000"
                         :min="ragne_1_start"
                         :max="parseInt(range_1)"  @change="propvalchng()"></el-slider>
                    </div>
                </div>
            </el-col>

            <el-col :span="3" :offset="1">
                <div class="grid-content bg-purple">
                    <div class="grid-content bg-purple-light">
                        <el-input placeholder="Please input" v-model.trim.number="perUnit" >
                            <template slot="append">{{miniunit}}</template>
                        </el-input>
                        <div class="block">
                            <el-slider v-model="perUnit"  :max="20" >
                            </el-slider>
                        </div>
                    </div>
                </div>
            </el-col>


            <el-col :span="3" :offset="1">
                <div class="grid-content bg-purple">
                    <div class="grid-content bg-purple-light">
                        <el-select v-model="stamdutyValue" placeholder="Select"  @change = "propertyStampDutyOnSelection">
                            <el-option
                                    v-for="item in PropertyTypesoptions"
                                    :key="item.value"
                                    :label="item.label"
                                    :value="item.value"
                            >
                            </el-option>
                        </el-select>
                    </div>
                </div>
            </el-col>
        </el-row>

        <!--annual rent-->

        <el-row :class="elrowtarget">
            <!--property area-->
            <el-col :span="6">

                <div class="grid-content bg-purple"></div>Annual Rent</el-col>
               
            <el-col :span="6">

                <div class="grid-content bg-purple-light">

                    <el-input placeholder="Please input" @change="annualRentchng()" v-model.trim.number="annualRentValue">
                         <template slot="prepend">
                             (£)
                          </template>
                    </el-input>
                    <template slot="prepend">(£) </template>
                    <div class="block">

                        <el-slider v-model="annualRentValue" :max="parseInt(range_2)" @change="annualRentchng()">

                        </el-slider>



                    </div>

                </div>

            </el-col>

            <el-col :span="6" :offset="1">

                <div class="grid-content bg-purple">



                    <div class="grid-content bg-purple-light">

                        <el-input placeholder="Please input" v-model.trim.number="anual_rent_perUnit" >
                            <template slot="append">{{miniunit}}</template>
                        </el-input>

                        <div class="block">

                            <el-slider v-model="anual_rent_perUnit"  :max="20">

                            </el-slider>



                        </div>

                    </div>

                </div>



            </el-col>

            <el-col :span="4">

                <div class="grid-content bg-purple-light">

                    <!-- <el-button type="primary" icon="plus" ></el-button> -->

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

                        <el-slider  :max="parseInt(range_3)" @change="areachange()" v-model="propertyArea">

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
                                    >
                                        <template slot="append">%</template>
                                    </el-input>
                                    <div class="block">


                                    </div>
                                </div>
                            </div>

                        </el-col>
                        <el-col :span="4">
                            <div class="grid-content bg-purple-light">
                                <!-- <el-button type="primary" icon="plus"></el-button> -->
                            </div>
                        </el-col>
                    </el-row>
                    <!--annual rent-->
                    <el-row>
                        <!--property area-->
                        <el-col :span="6"><div class="grid-content bg-purple"></div>Stamp Duty</el-col>
                        <el-col :span="6">
                            <div class="grid-content bg-purple-light">
                                <!--piko-->
                                <el-input placeholder="Please input" v-model="stampDutyType" disabled></el-input>
                                <div class="block">


                                </div>
                            </div>
                        </el-col>
                        <el-col :span="6" :offset="1">
                            <div class="grid-content bg-purple">

                                <div class="grid-content bg-purple-light">
                                    <el-input placeholder="Please input" v-model="stampDutyTypePercentage" disabled>
                                        <template slot="append">%</template>
                                    </el-input>
                                    <div class="block">
                                        <!--<el-slider
                                          v-model="value8"
                                          :step="10"
                                          :max="2000"
                                          >
                                        </el-slider>-->

                                    </div>
                                </div>
                            </div>

                        </el-col>
                        <el-col :span="4">
                            <div class="grid-content bg-purple-light">
                                <!--  <el-button type="primary" icon="plus"></el-button> -->
                            </div>
                        </el-col>
                    </el-row>
                    <el-row>
                        <!--legal fees-->
                        <!--rainbow-->
                        <el-col :span="6"><div class="grid-content bg-purple"></div>Legal Fees</el-col>
                        <el-col :span="6">
                            <div class="grid-content bg-purple-light">
                                <el-input placeholder="Please input" v-model.trim.number="LegalFeesPercentage" >
                                    <template slot="append">%</template>
                                </el-input>
                                <div class="block">


                                </div>
                            </div>
                        </el-col>
                        <el-col :span="6" :offset="1">
                            <div class="grid-content bg-purple">

                                <div class="grid-content bg-purple-light">
                                    <el-input placeholder="Please input" v-model.trim.number="com_legal_fees"></el-input>
                                    <div class="block">
                                        <!--<el-slider
                                          v-model="com_legal_fees"
                                          :step="10"
                                          :max="2000"
                                          >
                                        </el-slider>
                                         -->
                                    </div>
                                </div>
                            </div>

                        </el-col>
                        <el-col :span="4">
                            <div class="grid-content bg-purple-light">
                                <!--  <el-button type="primary" icon="plus"></el-button> -->
                            </div>
                        </el-col>
                    </el-row>
                    <el-row>
                        <!--legal fees-->

                        <el-col :span="6"><div class="grid-content bg-purple"></div>Agency Fees</el-col>
                        <el-col :span="6">
                            <div class="grid-content bg-purple-light">
                                <el-input placeholder="Please input" v-model.trim.number="AgencyFees" >
                                    <template slot="append">%</template>
                                </el-input>
                                <div class="block">


                                </div>
                            </div>
                        </el-col>
                        <el-col :span="6" :offset="1">
                            <div class="grid-content bg-purple">

                                <div class="grid-content bg-purple-light">
                                    <el-input placeholder="Please input" v-model.trim.number="com_agency_fees" disabled></el-input>
                                    <div class="block">
                                        <!--<el-slider
                                          v-model="propertyArea"
                                          :step="10"
                                          :max="2000"
                                          >
                                        </el-slider>-->

                                    </div>
                                </div>
                            </div>

                        </el-col>
                        <el-col :span="4">
                            <div class="grid-content bg-purple-light">
                                <!-- <el-button type="primary" icon="plus"></el-button> -->
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
                </el-input>
            </div>
            </el-col>
            <el-col :span="6"><div class="grid-content bg-purple"><!-- <el-button type="primary" icon="plus"></el-button> --> </div></el-col>
        </el-row>
         <multistamp
           :propertyValue="parseInt(propertyValue)" @multiple_stamp_duty_changed='multi_stamp_front'
           ></multistamp>
           <stamp
            :propertyValue="parseInt(propertyValue)"
            @single_stamp_duty_changed ='single_stamp_front'
           ></stamp>
           <commercialStampDuty
            :propertyValue="parseInt(propertyValue)" 
              @commercial_stamp_duty_changed ='commercial_stamp_front'
           ></commercialStampDuty>
           
        <!--<el-row>
            <el-collapse accordion>
             <el-collapse-item name="1">
   <template slot="title">
      Yield Sensitivity
   </template>-->
        <!--row 1-->
        <!--<el-row>-->
        <!--property value-->

        <!--<div class="block">
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
        <el-row>-->
        <!--year 1-->
        <!--<el-col :span="4"><div class="grid-content bg-purple">
            <el-input placeholder="Please input" v-model="com_y1_sensitivity">
              </el-input>
              </div>
              </el-col>-->
        <!--year 2-->
        <!--<el-col :span="4">
          <div class="grid-content bg-purple-light">
              <el-input placeholder="Please input" v-model="com_y2_sensitivity"></el-input>
              <div class="block">
                   
                </div>
             </div>
        </el-col>-->
        <!--year 3-->
        <!--<el-col :span="4" :offset="1">
          <div class="grid-content bg-purple">

            <div class="grid-content bg-purple-light">
              <el-input placeholder="Please input" v-model="com_net_yield"></el-input>
              <div class="block">
                </div>
             </div>
          </div>
            
        </el-col>-->
        <!--year 4-->
        <!--<el-col :span="4">
          <div class="grid-content bg-purple-light">
             <el-input placeholder="Please input" v-model="com_y4_sensitivity"></el-input>
          </div>
        </el-col>-->
        <!--year 5-->
        <!--<el-col :span="4">
          <div class="grid-content bg-purple-light">
             <el-input placeholder="Please input" v-model="com_y5_sensitivity"></el-input>
          </div>
        </el-col>
    </el-row>-->
        <!--row 2-->
        <!--<el-row>-->
        <!--year 6-->
        <!--<el-col :span="4"><div class="grid-content bg-purple">
            <el-input placeholder="Please input" v-model="com_y1_sensitivity_val">
              </el-input>
              </div>
              </el-col>
               <!--year 7-->
        <!--<el-col :span="4">
          <div class="grid-content bg-purple-light">
              <el-input placeholder="Please input" v-model="com_y2_sensitivity_val"></el-input>
              <div class="block">
                   
                </div>
             </div>
        </el-col>-->
        <!--year 8-->
        <!--<el-col :span="4" :offset="1">
          <div class="grid-content bg-purple">

            <div class="grid-content bg-purple-light">
              <el-input placeholder="Please input" v-model="propertyValue"></el-input>
              <div class="block">
                </div>
             </div>
          </div>
            
        </el-col>-->
        <!--year 9-->
        <!--<el-col :span="4">
          <div class="grid-content bg-purple-light">
             <el-input placeholder="Please input" v-model="com_y4_sensitivity_val"></el-input>
          </div>
        </el-col>-->
        <!--year 10-->
        <!--<el-col :span="4">
          <div class="grid-content bg-purple-light">
             <el-input placeholder="Please input" v-model="com_y5_sensitivity_val"></el-input>
          </div>
        </el-col>
    </el-row>-->
        <!--</el-collapse-item>
      </el-collapse>
     </el-row>
  </el-row>-->
    </div>

</template>

<script>
    import stamp from './StampDuty/singleStampDuty.vue'
    import multistamp from './StampDuty/MultiStampDuty.vue'
    import commercialStampDuty from './StampDuty/CommercialStampDuty.vue'

 window.big = require('big-integer')

    window.previousGoal = null
    export default {
       components:{
                stamp,
            multistamp,
            commercialStampDuty
       },
        data() {

            return {
                range_1_start:0,
                range_2_start:0,
                range_3_start:0,
                range_1:10000,
                range_2:2000,
                range_3:2000,
                stamdutyValue:'',
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
                LegalFeesPercentage: 0.75,
                LoanTermsYearValue:0,
                AgencyFees: 1.00,
                unit: 'Sq. meter',
                stampDutyType:0,
                
                currentHighLightValue:'',
                miniunit:'Sq. meter',
                options: [{

                    value: 0,

                    label: 'Sq Meters'

                }, {

                    value: 1,

                    label: 'Sq Feet'

                },
                ],
                PropertyTypesoptions:[
                    {
                        value: '0',
                        label: 'Single Property'
                    },
                    {
                        value: '1',
                        label: 'Multi Property'
                    }, {
                        value: '2',
                        label: 'Commercial Property'
                    }
                ],
                value: ''

            }

        },



        computed: {
            stampDutyTypePercentage(){
              
                return parseFloat((this.stampDutyType/this.propertyValue)*100).toFixed(2)
            },
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
                    return this.comp_ps_properVal;
                }


            },

            anual_rent_perUnit() {
                if(!isNaN(this.comp_ps_annualRent) && isFinite(this.comp_ps_annualRent))
                    return parseFloat(this.comp_ps_annualRent) ;
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

                return this.propertyValue * this.LegalFeesPercentage * .01;

            },

            com_agency_fees() {

                return this.propertyValue * this.AgencyFees * .01;

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
            com_y1_sensitivity_val() {

                var d = 100 * (this.annualRentValue / (parseFloat(this.propertyValue) + parseFloat(this.com_gross)));
                var k = Math.abs(d - 2 * this.YieldSensitivityIncreamentValue);
                var b = parseInt(this.propertyValue)*k*.01;
                if(!isNaN(k)||isFinite(k)) return b;
                return  0;

            },

            com_y2_sensitivity_val() {

                var d = 100 * (this.annualRentValue / (parseFloat(this.propertyValue) + parseFloat(this.com_gross)));

                var c =  Math.abs(d - this.YieldSensitivityIncreamentValue) ;
                var b = parseInt(this.propertyValue)*c*.01;
                if(!isNaN(c)||isFinite(c))
                    return b;

                return 0;

            },

            com_y4_sensitivity_val() {

                var d = 100 * (this.annualRentValue / (parseFloat(this.propertyValue) + parseFloat(this.com_gross)));

                var j = Math.abs(d + this.YieldSensitivityIncreamentValue);
                var b = parseInt(this.propertyValue)*j*.01;
                if(!isNaN(j)||isFinite(j)) return b;
                return 0;

            },

            com_y5_sensitivity_val() {

                var d = 100 * (this.annualRentValue / (parseFloat(this.propertyValue) + parseFloat(this.com_gross)));
                var c = Math.abs(d + 2 * this.YieldSensitivityIncreamentValue);
                if(!isNaN(c)||isFinite(c)) return c;
                return 0;

            },


            elrowtarget(){
                if (this.currentHighLightValue!='')
                {
                    this.currentHighLightValue=''
                    return 'el-row-target'
                }
                return 'el-row'
            },
        },

        methods: {

            // highlight_property_value(ev)
            // {
            //    var g = ev.target.parentElement
            //    var d = g.parentElement
            //    var c = d.parentElement
            //    if(window.previousGoal==undefined||window.previousGoal==null)
            //     window.previousGoal = c;
            //    var p = c.className.split(' ').includes('el-row-target')
            //    console.log(window.previousGoal)
            //    if(p) { 
            //      window.previousGoal.className='el-row'
            //    }
            //    else c.className ='el-row el-row-target'
            //   this.currentHighLightValue='property' 
            // },
            // highlight_annual_rent(){
            //     this.currentHighLightValue='annualrent' 
            // },
            propertyStampDutyOnSelection()
            {

                switch(this.stamdutyValue){
                    case  '0':
                        this.stampDutyType = window.singleStampDuty
                        console.log('stamping',this.stampDutyType)
                        break;
                    case  '1' :
                        this.stampDutyType = window.MultiStampDuty
                        console.log('stamping multi',this.stampDutyType)
                        break;
                    case '2' :
                        this.stampDutyType = window.commercialStampDuty
                        console.log('stamping commercial',this.stampDutyType)
                        break;
                    default:
                        break;
                }
             /*----------------------------------------------------------------------------------------*/ 
            },
            unitchange(){
                if(!this.__ispa)
                {
                    return 0;
                }
                else  if(this.unit==0 && this.__ispa) {
                    this.miniunit = 'sqMeter'
                    var p= this.propertyArea /10.76;
                    return this.comp_ps_properVal + ' $' + this.unit;
                }
                else {
                    if(this.__ispa)
                        this.miniunit = 'sqFeet'
                    var g = this.propertyArea *10.76;
                    return (this.comp_ps_properVal *10.76)+ ' $' + this.unit;
                }
            },
            propvalchng( ) {
                if(this.propertyValue>= 9000 && this.propertyValue<100000000)
                 {
                    this.range_1_start = big(this.range)
                    this.range_1+=big(100000)
                    }
                else {
                    this.range_1 = 10000
                    this.range_1_start = 0;
                }
                this.$emit('propertyValueinput', this.propertyValue)
            },
            propvalSliderchng() {
                console.log('perunit changed..',newval)
                // var d = parseFloat(this.propertyValue /= parseFloat(newval))
                // this.propertyValue = d
                this.$emit('propertyValueinput', this.propertyValue)
            },
            annualRentchng() {
                if(this.annualRentValue>=1900) this.range_2+=2000
                else this.range_2 = 2000
                this.$emit('annualRentValueinput', this.annualRentValue)

            },
            com_net_yield_change(){
                console.log('net yield update...',)
            },
            areachange() {
                if(this.propertyArea>=1900) this.range_3+=2000
                else this.range_3 = 2000
                // this.propertyValue = parseFloat(this.propertyValue)/5;
                this.$emit('propertyAreainput', this.propertyArea)

            },
            purchaserCostChange(){
                this.$emit('purchaserCostChange', this.purchaserCost)
            },
            multi_stamp_front(data){
                this.stampDutyType = data;
                 
               // alert('stamp multiple event fired')
            },
             single_stamp_front(data){
                this.stampDutyType = data;
                    if (this.__ispa)  this.stampDutyType = 0
               // alert('stamp multiple event fired')
            },
            commercial_stamp_front(data){
                this.stampDutyType = data;
                    if (this.__ispa)  this.stampDutyType = 0
               // alert('stamp multiple event fired')
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
        },
        mounted(){
            this.stampDutyType =0.0
            //this.stampDutyTypePercentage = 0.0
        }

    }
</script>

<style scoped >
    .el-row {
        margin-bottom: 20px;
        padding: 15px;
    /*background: #ffd972;*/
    &:last-child {

         margin-bottom: 0;

     }

    }
    .el-row-target {
        margin-bottom: 20px;
        padding: 15px;
        background: #ffd972;
    &:last-child {

         margin-bottom: 0;

     }

    }
</style>
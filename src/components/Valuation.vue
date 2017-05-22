<template>
 <!--property value-->
  <div> 
      <el-row>
         <!--property value-->
          <el-col :span="6"><div class="grid-content bg-purple"></div>Property Value</el-col>
          <el-col :span="6">
            <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="input"></el-input>
                <div class="block">
                    <el-slider
                      v-model="value8"
                      step=10
                      max=2000
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
                      step=10
                      max=2000
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
                <el-input placeholder="Please input" v-model="input"></el-input>
                <div class="block">
                    <el-slider
                      v-model="value8"
                      step=10
                      max=2000
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
                      step=10
                      max=2000
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
                <el-input placeholder="Please input" v-model="input"></el-input>
                <div class="block">
                    <el-slider
                      v-model="value8"
                      step=10
                      max=2000
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
                      step=10
                      max=2000
                      >
                    </el-slider>
                     
                  </div>
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
          <el-col :span="6"><div class="grid-content bg-purple"></div>Property Value</el-col>
          <el-col :span="6">
            <div class="grid-content bg-purple-light">
                <el-input placeholder="Please input" v-model="input"></el-input>
                <div class="block">
                    <el-slider
                      v-model="value8"
                      step=10
                      max=2000
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
                      step=10
                      max=2000
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
                <el-input placeholder="Please input" v-model="input"></el-input>
                <div class="block">
                    <el-slider
                      v-model="value8"
                      step=10
                      max=2000
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
                      step=10
                      max=2000
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
  <el-col :span="6"><div class="grid-content bg-purple">£1.,919,936,268,032,953,5e+,304</div></el-col>
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
                <el-input placeholder="Please input" v-model="input"></el-input>
                <div class="block">
                    <el-slider
                      v-model="value8"
                      step=10
                      max=2000
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
                      step=10
                      max=2000
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
                <el-input placeholder="Please input" v-model="input"></el-input>
                <div class="block">
                    <el-slider
                      v-model="value8"
                      step=10
                      max=2000
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
                      step=10
                      max=2000
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